# A2_220601023_FatmaCure
BYM412 Robotik Dersi - Fatma Cüre 220601023 - Ödev 2

Bu proje, ROS 2 Humble üzerinde çalışan basit bir mobil robotun Gazebo ortamında simülasyonunu ve Ball Chaser düğümü aracılığıyla top takibi davranışını içermektedir. Proje; robotun URDF modeli, sensör köprüleri, TF dönüşümleri ve görselleştirme araçlarını tek bir launch dosyası üzerinden çalıştıracak şekilde yapılandırılmıştır.

---

## Proje İçeriği

Proje aşağıdaki temel paketlerden oluşmaktadır:

- **my_robot_description**  
  Robotun URDF/Xacro modeli, world dosyası ve RViz konfigürasyon dosyalarını içerir.

- **my_robot_bringup**  
  Launch dosyaları ve simülasyonu başlatmak için gerekli yapılandırmaları içerir.

- **ball_chaser**  
  Kameradan gelen görüntü verisini işleyip robota `/cmd_vel` komutları gönderen takip düğümüdür.

---

## Gereksinimler

Bu proje **ROS 2 Humble** sürümü ile geliştirilmiştir.  
Aşağıdaki paketlerin yüklü olması gerekmektedir:

sudo apt install ros-humble-desktop ros-humble-gazebo-ros-pkgs ros-humble-ros-gz-bridge

## Kurulum Adımları
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src
git clone https://github.com/raycure/A2_220601023_FatmaCure
cd ~/ros2_ws
colcon build
source /opt/ros/humble/setup.bash
source ~/ros2_ws/install/setup.bash

## Çalıştırma
ros2 launch my_robot_bringup bringup.launch.py
