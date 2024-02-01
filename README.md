# ROS2-turtlebot

## 라즈베리파이 우분투 설치 

### ros2 배포판 있는 최신 우분투 버전 확인
여기서 확인 http://packages.ros.org/ros2/ubuntu/dists/<br/>
이 글을 작성하는 현재는 Ubuntu 22.04.3 LTS (Jammy Jellyfish)가 최신버전<br/>

### MicroSD카드 굽기
Raspberry Pi Imager 사용해서 Ubuntu22.04 server 버전을 설치한다.<br/>
![image](https://github.com/kutmslee/turtlebot3/assets/38107813/843848e5-7f32-474e-b15e-09a2da653a8d)<br/>
![image](https://github.com/kutmslee/turtlebot3/assets/38107813/5ac1c503-51bf-4b5c-ae45-ec66650fb52c)<br/>
![image](https://github.com/kutmslee/turtlebot3/assets/38107813/ab2e4a22-1bef-44b1-9d33-23d6b69ebf2e)&nbsp;
![image](https://github.com/kutmslee/turtlebot3/assets/38107813/2c297ddd-5443-4458-9a68-332ea48c00a6)

## PC 연결
PC에서 우분투 열고 ssh moses@turtlebot 한다.

### locale을 확인(안해도 됨)
moses@turtlebot:~$ localectl<br/>
&nbsp;System Locale: LANG=C.UTF-8<br/>
&nbsp;VC Keymap: (unset)<br/>
&nbsp;X11 Layout: kr<br/>
&nbsp;X11 Model: pc105<br/>
UTF-8을 지원하지 않으면 설치한다.

## ROS2 패키지 설치

### 시스템에 ROS2 apt repository 추가
이걸 하지 않으면 ros-humble-desktop 설치할 때 Unable to locate package ros-humble-desktop 라는 에러가 뜬다.

#### Ubuntu Universe 무료 및 오픈소스 소프트웨어 저장소 추가(안해도 됨)
moses@turtlebot:~$ sudo add-apt-repository universe<br/>
확인 방법은 moses@turtlebot:/etc/apt$ vi sources.list<br/>
&nbsp;deb http://ports.ubuntu.com/ubuntu-ports mantic main restricted universe multiverse<br/>
&nbsp;deb http://ports.ubuntu.com/ubuntu-ports/ mantic-updates main restricted universe multiverse<br/>
&nbsp;deb http://ports.ubuntu.com/ubuntu-ports/ mantic-security main restricted universe multiverse<br/>
vi 끝낼 때는 :q<br/>

#### curl(Client Url)설치(안해도 됨)
moses@turtlebot:~$ sudo apt update && sudo apt install curl -y<br/>

#### curl을 사용해서 ROS2 GPG Key 가져오기
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg<br/>

#### ROS2 GPG키 추가된 것을 확인
moses@turtlebot:~$ cd /<br/>
moses@turtlebot:/$ cd usr/share/keyrings<br/>
moses@turtlebot:/usr/share/keyrings$ ls<br/>
&nbsp;ros-archive-keyring.gpg &nbsp;&nbsp;&nbsp; ubuntu-master-keyring.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-esm-infra.gpg<br/>
&nbsp;ubuntu-archive-keyring.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-anbox-cloud.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-fips.gpg<br/>
&nbsp;ubuntu-archive-removed-keys.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-cc-eal.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-realtime-kernel.gpg<br/>
&nbsp;ubuntu-cloudimage-keyring.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-cis.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-ros.gpg<br/>
&nbsp;ubuntu-cloudimage-removed-keys.gpg  ubuntu-pro-esm-apps.gpg<br/>

#### 소스 목록에 repository 추가
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

#### 추가된 repository를 apt에 적용
sudo apt update<br/>
sudo apt upgrade<br/>

### ROS2 설치
sudo apt install ros-humble-desktop<br/>
이작업은 시간이 좀 걸린다. 20분 걸림<br/>
sudo apt install ros-humble-ros-base<br/>
sudo apt install ros-dev-tools<br/>












