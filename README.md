# ROS2-Humble

## locale을 확인한다.
moses@moses-turtlebot:~$ localectl<br/>
&nbsp;System Locale: LANG=C.UTF-8<br/>
&nbsp;VC Keymap: (unset)<br/>
&nbsp;X11 Layout: kr<br/>
&nbsp;X11 Model: pc105<br/>
UTF-8을 지원하지 않으면 설치한다.

## 시스템에 ROS2 apt repository 추가
Ubuntu Universe 저장소 추가 sudo add-apt-repository universe<br/>
curl(Client Url)설치 sudo apt update && sudo apt install curl -y<br/>
curl을 사용해서 ROS2 GPG Key 가져오기 sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg<br/>
cd /<br/>
cd usr/share/keyrings<br/>
moses@moses-turtlebot:/usr/share/keyrings$ ls<br/>
ros-archive-keyring.gpg             ubuntu-master-keyring.gpg   ubuntu-pro-esm-infra.gpg<br/>
ubuntu-archive-keyring.gpg          ubuntu-pro-anbox-cloud.gpg  ubuntu-pro-fips.gpg<br/>
ubuntu-archive-removed-keys.gpg     ubuntu-pro-cc-eal.gpg       ubuntu-pro-realtime-kernel.gpg<br/>
ubuntu-cloudimage-keyring.gpg       ubuntu-pro-cis.gpg          ubuntu-pro-ros.gpg<br/>
ubuntu-cloudimage-removed-keys.gpg  ubuntu-pro-esm-apps.gpg<br/>








