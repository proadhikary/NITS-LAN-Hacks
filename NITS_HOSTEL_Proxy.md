
## For linux:
#### Configure using GUI

Open the network settings and set the your system wide network proxy.
Network -> Network proxy -> Configure -> Apply system wide.
Keep the Socks Host Blank if you want to acess web.whatsapp.com.

Explanation: https://medium.com/@krish.raghuram/setting-up-proxy-in-ubuntu-95058da0b2d4

SERVER_BH12345678GH123: 172.16.199.40
SERVER_BH9ABCD: 172.16.2.11
PORT: 8080

#### Add the following lines to _~/.bashrc_

```
export http_proxy=http://172.16.199.40:8080/ 
export https_proxy=http://172.16.199.40:8080/ 
```

#### Add the following lines to _/etc/apt/apt.conf_

```
Acquire::http::Proxy "http://172.16.199.40:8080"; 
Acquire::https::Proxy "http://172.16.199.40:8080"; 
```

#### Add the following lines to _/etc/bash.bashrc_

```
export http_proxy=http://172.16.199.40:8080/ 
export https_proxy=http://172.16.199.40:8080/ 
```

#### Add the following lines to _/etc/environment_

```
export http_proxy="http://172.16.199.40:8080/"
export https_proxy="http://172.16.199.40:8080/"
```

#### Configuration for SNAP

```
sudo snap set system proxy.http="http://172.16.199.40:8080"
sudo snap set system proxy.https="http://172.16.199.40:8080"
```

#### For git
```
git config --global --unset http.proxy
git config --global http.proxy http://172.16.199.40:8080
git config --global --get http.proxy
```

#### For npm
```
npm config set http-proxy http://172.16.199.40:8080
npm config set https-proxy http://172.16.199.40:8080
```

<br><br>
## For Windows:
#### Configure using GUI
Open the network settings and set the proxy and port
Proxy: 172.16.199.40
Port: 8080

#### For conda
To change environment variables on Windows:
1. In the Start menu, search for “env”.
2. Select “Edit Environment Variables for your account”
3. Select “Environment Variables…”
4. Press “New…”
5. Add two variables http_proxy and https_proxy both with the same value: http://172.16.199.40:8080
