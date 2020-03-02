# 1. Install clash, proxydriver and proxychains-ng
```shell
yay -S clash proxydriver

sudo pacman -S proxychains-ng
```
# 2. Config them
## clash


- Firstly, the clash config-file is in the path `~/.config/clash/config.yaml`. If it does not exit, you can create it.

- Then, you can use `vim` to open the file to get (or set) proxy port.
```shell
vim ~/.config/clash/config.yaml
```
## proxydriver
The config file of proxydriver is `/etc/proxydriver.d/your_SSID.conf`. According to the clash config file, you can change the proxydriver's config file.
## proxychains-ng
When you need proxy your shell, you can do this:
```shell
proxychains wget https://www.google.com
```
In short, adding the `proxychains` in front of your command line, that's easy.
## proxy ssh
```shell
ssh -o Proxycommand="nc -X 5 -x proxy.net:1080 %h %p" user@server.net
```
# 3. Run clash
Run the above command:
```shell
nohup clash &
```
# 4. Set your browser(optional)
Make sure your bowser's proxy settings are th same with the clash file. (Maybe some browser don't need to do this.) 
# 5. Set clash autostart
Create a link for clash in `~/.config/autostart-scripts/`. Now you can autostart clash.
