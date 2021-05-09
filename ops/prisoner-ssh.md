# SSH

## Accessing SSH without full webOS SDK (prisoner)

> **Warning:** If you are already rooted, installing the Devmode app may replace the contents of your `start-devmode.sh`.

> If you are already rooted, you can just add your ssh public key to the list of authorized keys of the prisoner user.

If you want to connect to the TV via SSH as the `prisoner` user (for devmode) using the official Devmode app and without installing the full SDK, follow the following steps:

**On the TV:**
1. Install the Devmode app in your TV
2. Login with your developer account
3. Enable devmode
4. Enable keyserver

**On your computer:**

3. Set the `$tv` environment variable with your TV's IP address:

```
# replace with the IP address of your TV
tv=10.11.12.13
```

4. Download the key and decrypt it using the passphrase displayed on your TV screen:

```sh
# create this directory if it does not exist already
cd ~/.ssh/

openssl rsa -in <(curl http://$tv:9991/webos_rsa) > webos_rsa && chmod 600 webos_rsa
```

5. Connect via ssh:

```
ssh prisoner@$tv -i webos_rsa -p 9922 bash -i
```

**Note:** This will download your TV's prisoner user's private key (`webos_rsa`) to the directory where you are running the commands from (in this case, it is in `~/.ssh/`). 

**Tip:** The @webosose/ares-cli npm package is sufficient to play with webOS TV development. (ares-package, ares-install, ares-launch...)


Credits: [Informatic](https://gist.github.com/Informatic/1983f2e501444cf1cbd182e50820d6c1)