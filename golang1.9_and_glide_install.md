Golang 및 glide (패키지매니저) 다운로드 및 설치 , 세팅. 

**Golang 다운로드 및 설치 , 세팅. **

https://golang.org/dl/ 

에서 다운로드 한다.
중요한것은 GOPATH 를 설정하는것이다.

예제는 ubuntu 기준으로 함.

```
$ wget https://redirector.gvt1.com/edgedl/go/go1.9.2.linux-amd64.tar.gz
$ tar xvf go1.9.2.linux-amd64.tar.gz
$ cp -rp go /usr/lib/go-1.9.2

```
전체 적용을 위해서.
/etc/profile/goenv.sh  파일 생성.

```
#!/bin/sh
export PATH=/usr/lib/go-1.9.2/bin:$PATH
export GOROOT=/usr/lib/go-1.9.2
```

사용자 로컬의 ~/.profile 에 추가해도 됨.
적용하기 위해서는 

```
$ source /etc/profile.d/goenv.sh
하고,

$ which go
로 설치 위치 확인할것.

$ go version   
으로 version 확인할것.
go version go1.9.2 linux/amd64

$ mkdir ~/go
하여 go src archive 를 만들것.

```

$HOME/go/bin 을 사용자의 ~/.profile  or  ~/.bashrc 에
추가할것.

```
export PATH=$HOME/go/bin:$PATH
```

또한, $HOME/go  디렉토리에 package 개발용 
**go package manager glide 설치**

https://github.com/Masterminds/glide

```
curl https://glide.sh/get | sh
```
또는
On Ubuntu Precise (12.04), Trusty (14.04), Wily (15.10) or Xenial (16.04) you can install from our PPA:
```
sudo add-apt-repository ppa:masterminds/glide && sudo apt-get update
sudo apt-get install glide
```

또는 

wget https://github.com/Masterminds/glide/releases/download/v0.13.0/glide-v0.13.0-linux-amd64.tar.gz

tar xvzf glide-v0.13.0-linux-amd64.tar.gz

cp linux-amd64/glide /usr/bin
cp linux-amd64/glide /usr/lib/go-1.9.2/bin
```
해서 사용할것.


