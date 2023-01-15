## 2022.12.27
  노트북 하나 밀고 CentOS 7 설치<br>
  부팅 USB 만들고, 노트북 포맷 후 CentOS 설치 , 그리고 yum 패키지 업그레이드
  
  1. GUI 설정 추가 (VS Code 로 코드 수정 작업도 하기 위함)<br>
    https://emgblog.tistory.com/30 <br>
    VS Code 같은거 설치 할 때, 이상하게 '뭔가가 잘못되었습니다' 하면서 설치파일이 다운받아 지지 않아서, yum 혹은 wepget + localinstall 로 진행. 
  
  2. 네트워크 무선랜 설정 잡아주기 <br>
    https://musclebear.tistory.com/90
  
  3. C 드라이브에 CentOs 는 설정했는데, D 드라이브를 마운트 해야함. <br>
    1) 일단 D 드라이브의 File System 이  NFTS 였기 떄문에 변경후 마운트 <br>
      https://www.lesstif.com/system-admin/linux-ntfs-mount-59343146.html <br>
    2) 이걸 재부팅 할떄마다 자동으로 할수 있게끔 작업 <br>
      https://tibyte.kr/242 <br>
      -> 이거 할때 위에꺼 따라 한다고 파티션 타입을 그냥 xfs 로 같이 달아주면 emergency mode 로 진입함, 이러면 침착하게 설정파일 수정해주면 됨 <br>
  4. git 설치 ( 근데 그냥 yum 에서는 1.xx 를 지원하기에 서드파티 저장소를 이용한 2.xx 버전 설치 ) <br>
    https://phodobit.kr/53

## 2023.01.08
  노트북에 SSL 설정 및 Node.js(Express) 에 https 설정 => 핸드폰으로 사이트 접속 하기 위해서<br>
  해당 작업 nginx 도입 후 nginx 로 이관 및 포트포워딩 까지 작업 할것 ( 공유기 계정 획득 완료 )
  

## 2023.01.15
  Cent OS 에 Slack 이 필요해져서 설치를 하는데 애를 많이 먹음.. <br/>
  1. 인터넷 slack 창으로 가서 설치 <br/>
  2. .rpm 까지는 문제없이 받았으나, 자꾸 "유감스럽게도 뭔가가 잘못되었습니다" 라고 뜸 <br/>
  3. 그래서 파일 받은곳 가서 sudo rpm -ivh ~.rpm 을 했는데 </br>
      경고: slack-4.29.149-0.1.el8.x86_64.rpm: Header V4 RSA/SHA512 Signature, key ID 7eb66c16: NOKEY</br>
      오류: Failed dependencies:</br>
	      libXScrnSaver is needed by slack-4.29.149-0.1.el8.x86_64</br>
	      libappindicator-gtk3 is needed by slack-4.29.149-0.1.el8.x86_64</br>
        라고 뜨면서 안됨..</br>
      CentOS 7 GPG Key 도 받아보고 했지만 정상적으로 수행이 안됨.. 아직 원인 해결 못했으나 libScrnSaver 가 없어서 인듯</br>
  4. 결국 .rpm 받은 자리에서 sudo yum localinstall ./slack-*.rpm 으로 설치 완료
  5. 참고 자료 [Rpm Header V4 RSA/SHA1 Signature, key ID … NOKEY](https://velog.io/@zeesoo/Linux-yum-error-rpmtsHdrFromFdno-Header-V3-RSASHA1-Signature-key-ID-c105b9de-NOKEY-%ED%95%B4%EA%B2%B0%EB%B0%A9%EB%B2%95) 
  
