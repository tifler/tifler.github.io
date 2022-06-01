---
title:  "Install Jetson Nano"
toc: true
tags:
 - JetsonNano
 - nvidia
 - howto
 - sd
---

***Jetson Nano에 사전 빌드된 SD 카드 이미지를 설치하는 과정을 설명합니다.***

## 준비사항
* Jetson Nano - Package에는 보드만 포함되고 나머지는 별도!!
* USB 마이크로 B 타입 커넥터
* 2A 이상의 USB 충전기
* 16GB 이상의 마이크로 SD 카드
* 마이크로 SD 카드 리더기
* PC (이 포스트는 Mac을 기준으로 작성됨)
* 모니터 및 HDMI 케이블
* USB 키보드, USB 마우스, 유선 LAN 혹은 USB WiFi 동글

## 참고 사이트
[Get Started Jetson Nano DevKit](https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit)

---

## 1. 이미지 다운로드

* [Download Pre-built SD Card Image](https://developer.nvidia.com/jetson-nano-sd-card-image-r3231)
    * Etcher 사용시 Zip 파일 압축해제 불필요

## 2. 마이크로 SD 카드에 Flash 하기
* Flash 툴인 [Etcher 다운로드](https://www.balena.io/etcher/)

* 다운로드된 zip 파일을 이용해 SD 카드 flash 하기 (12GB로 확장됨)
![Image Alt Flash](/assets/images/2020-01-18/Flash.png)
* 자동으로 verification이 이루어 지는 화면
![Image Alt Verify](/assets/images/2020-01-18/Verify.png)

## 3. 전원연결 및 설정
* 기본적인 Ubuntu 설정과 동일

## 4. 커스텀 설정

* Swap 파일 생성 (4GB)

```
sudo fallocate -l 4G /var/.swap
sudo chmod 600 /var/.swap
sudo mkswap /var/.swap
sudo swapon /var/.swap
sudo bash -c 'echo "/var/.swap swap swap defaults 0 0" >> /etc/fstab'
```

