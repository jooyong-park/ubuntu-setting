cgroup-util 설치 방법
=====================

1.	cgroup-util 지원 사양
2.	커널 버전 4.6.x 업그레이드 하기
3.	python pip 설치 환경 설정 하기
4.	cgroup-util 설치

#### 1. cgroup-util 지원 사양

##### Supported Linux Version

-	4.6.y

	##### Supported Python

-	python2: 2.6 and above

-	python3: 3.4 and above

	-	3.0 to 3.3 may work but not tested

#### 2. 커널 버전 4.6.x 업그레이드 하기

우분투 16.04버전의 커널 버전 업그레이드 방법 - 우분투 16.04 데스크탑 버전

```
  $ sudo apt-get install --install-recommends linux-generic-hwe-16.04 xserver-xorg-hwe-16.04
```

-	우분투 16.04 서버 버전 sudo apt-get install --install-recommends linux-generic-hwe-16.04

```
  $  cat /proc/version
  $  aptitude update
  $  sudo apt install aptitude
  $  aptitude update
  $  sudo aptitude update
  $  sudo aptitude safe-upgrade
  $  sudo aptitude search linux-headers-4.8
  $  sudo apt-get install --install-recommends linux-generic-hwe-16.04 xserver-xorg-hwe-16.04
  $  cat /proc/version
  $  sudo update-grub
  $  sudo reboot
  $  cat /proc/version
```

#### 3. python pip 설치 환경 설정 하기

```
	$ sudo apt install python-pip
	$ pip list(정상 설치 확인)
```

#### 4. cgroup-util 설치

-	사용자 설치

```
  $ sudo pip install cgroup-utils
```

-	개발자 설치

```
  $ git clone git://github.com/peo3/cgroup-utils.git
  $ cd cgroup-utils
  $ python setup.py build
  $ sudo python setup.py install
```

#### 참조 링크 :

-	http://www.fernandoalmeida.net/blog/how-to-limit-cpu-and-memory-usage-with-cgroups-on-debian-ubuntu/

[참조] 커널 버전 변경 방법
--------------------------

For 64bit ONLY.

In Terminal:

```
  $ cd Desktop
  $ mkdir linux_14.10.1
  $ cd linux_14.10.1
  $ wget kernel.ubuntu.com/~kernel-ppa/mainline/v4.10.1/linux-headers-4.10.1-041001-generic_4.10.1-041001.201702260735_amd64.deb
  $ wget kernel.ubuntu.com/~kernel-ppa/mainline/v4.10.1/linux-image-4.10.1-041001-generic_4.10.1-041001.201702260735_amd64.deb
```

Install the 4.10.1 Linux-Kernel:

```
  $ sudo dpkg -i *.deb
```

Update GRUB:

```
  $ sudo update-grub
```

Don't forget to install (to avoid any software error in the future) the "gcc" from synaptics according to the Linux-kernel x.xx version

```
  $ sudo reboot
```

Now choose to boot your 4.10.1 Linux-kernel from GRUB menu.
