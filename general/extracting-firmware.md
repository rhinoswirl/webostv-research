# Extracting the TV Firmware

It may be useful to extract the TV firmware in order to properly reverse engineer it instead of going through exploring all the files manually.

For this, you need 2 things: 

- The TV firmware update file
- epk2extract

## Retrieving the TV firmware update file

You may be able to download the epk update file directly from the support page of your TV Model in the LG's support page.

If no download options are available, you will need to sniff communication between the TV and `sn.lge.com` / `snu.lge.com` on startup to extract .epk download URL.

For this you may need to lower your current version in the HTTP Request if you don't have any updates pending.

Depending on the firmware version, this request will be done over HTTP for older versions and HTTPS for newer ones.


## Using epk2extract

[epk2extract](https://github.com/openlgtv/epk2extract) is a tool that can extract, decrypt, convert multiple file formats that can be found in LG TV sets and similar devices.

In order to use it, it needs to compile it first by following the instructions available on the projects page.

If the key for that specific model is already added to epk2extract you can unpack it straight away. Otherwise you need root to dump that key to extract it.


If you want to use Docker, follow the following steps:

1. Create the following Dockerfile

```
FROM debian:stretch-slim
RUN apt update
RUN apt-get install -y git build-essential cmake liblzo2-dev libssl-dev libc6-dev zlib1g-dev
RUN mkdir /srcs
WORKDIR /srcs
RUN git clone https://github.com/openlgtv/epk2extract.git
WORKDIR /srcs/epk2extract
RUN chmod +x build.sh
RUN ./build.sh
ENTRYPOINT ["tail", "-f", "/dev/null"]
```

2. Build and tag the image

```
docker build -t openlgtv/epk2extract:latest .
```

3. Start it

```
docker run openlgtv/epk2extract
```

4. Copy the required firmware files to the container (Use `docker ps` to get the container ID)

```
docker cp /path/to/your/starfish-dvb-secured.epk 4eed468a8169:/srcs/epk2extract/build_linux/firmware.epk
```


5. Run the extract tool 
```
./epk2extract firmware.epk
```

6. Copy the files back from the container
```
docker cp 4eed468a8169:/srcs/epk2extract/build_linux/YOUR_EXTRACTED_FIRMWARE firware-extracted
```

Please feel free to update this Dockerfile to use proper volumes instead of needing to copy files to/from the container.

