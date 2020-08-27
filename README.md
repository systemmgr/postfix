## postfix  
  
Postfix attempts to be fast, easy to administer, and secure mail server  
  
requires:    
```
apt install postfix mailutils
```  
```
yum install postfix mailx
```  
```
pacman -S postfix s-nail
```  
  
Automatic install/update:
```
sudo bash -c "$(curl -LSs https://github.com/systemmgr/postfix/raw/master/install.sh)"
```
Manual install:
```
sudo mv -fv "/usr/local/etc/postfix" "/usr/local/etc/postfix.bak"
sudo git clone https://github.com/casjay-dotfiles/postfix "/usr/local/etc/postfix"
sudo find /usr/local/etc/postfix/main.cf -type f -exec sed -i "s#MYHOSTNAME#$(hostname -s)#g" {} \; >/dev/null 2>&1
sudo ln -sf /usr/local/etc/postfix/* /etc/postfix/
sudo ln -sf /usr/local/etc/postfix/aliases /etc/aliases
sudo postmap /etc/postfix/{access,canonical,relocated,transport,virtual}
sudo newaliases
sudo systemctl restart postfix
```
  
  
<p align=center>
  <a href="https://wiki.archlinux.org/index.php/postfix" target="_blank">postfix wiki</a>  |  
  <a href="http://www.postfix.org/" target="_blank">postfix site</a>
</p>  
    
