透過apt-get來安裝docker engine

<pre><code>sudo apt-get update

sudo apt-get install docker.io</code></pre>

docker 的指令都是以root來執行的，每次下指令時都要加上sudo 會有點麻煩，執行以下指令來提高權限

<pre><code>sudo groupadd docker
sudo usermod -aG docker $USER</code></pre>

將docker設定成每次開機自動啟動
<pre><code>sudo systemctl enable docker</code></pre>
