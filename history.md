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
