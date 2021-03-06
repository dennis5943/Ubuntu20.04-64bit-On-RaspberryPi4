# Ubuntu20.04-64bit installation on Raspberry Pi 4
在樹苺派上安裝Ubuntu20.04 Server

<h2>1.下載Ubuntu20.04 Image</h2>

[官網下載](https://ubuntu.com/download/raspberry-pi)

<h2>2.將Image 燒至SD Card</h2>

可使用balenaEtcher工具，三步完成 [官網連結](https://www.balena.io/etcher/)

<h2>3.第一次登入</h2>

用UserName: ubuntu ; Password: ubuntu第一次登入，並修改密碼

<h2>(Option)設定wifi</h2>

可參照[此篇](https://linuxconfig.org/ubuntu-20-04-connect-to-wifi-from-command-line)
  
  設定檔會放在本機的/etc/netplan/ 路徑
  
  <pre><code>sudo nano /etc/netplan/50-cloud-init.yaml</code></pre>
  
  修改成這樣
  
  <pre><code>
  network:
    ethernets:
        eth0:
            dhcp4: true
            optional: true
    version: 2
    wifis:
        wlp3s0:
            optional: true
            access-points:
                "SSID-NAME-HERE":
                    password: "PASSWORD-HERE"
            dhcp4: true
   </code></pre>
   
   存檔後重整網路(--debug會在設定檔有誤時顯示錯誤資訊)
   
   <pre><code>
   $ sudo netplan --debug apply
   </code></pre>

<h2>(Option)新增使用者</h2>

[參考網址](https://www.digitalocean.com/community/tutorials/how-to-create-a-sudo-user-on-ubuntu-quickstart)

<pre><code>adduser [user name]
usermod -aG sudo username</code></pre>
