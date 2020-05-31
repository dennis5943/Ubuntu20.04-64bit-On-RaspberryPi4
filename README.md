# Ubuntu20.04-64bit-On-RaspberryP4
在樹苺派上安裝Ubuntu20.04 Server

1.官網下載Ubuntu20.04 Image (https://ubuntu.com/download/raspberry-pi)

2.將Image 燒至SD Card，可使用balenaEtcher工具，三步完成 (https://www.balena.io/etcher/)

3.用UserName: ubuntu ; Password: ubuntu第一次登入，並修改密碼

4.設定wifi，可參造此篇(https://linuxconfig.org/ubuntu-20-04-connect-to-wifi-from-command-line)
  
  設定檔會放在本機的/etc/netplan/ 路徑
  
  sudoedit /etc/netplan/50-cloud-init.yaml
  
  修改成這樣
  
  <pre><code>This is a code block.

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
