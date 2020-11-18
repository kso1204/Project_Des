# Project

private에 지금까지 진행 한 행사를 전부 올려 두었으나 확인이 불가하여

세 개의 프로젝트에 대해서만 간략하게 GCP에 올려 구동한 상태입니다.

2018년 (입사 시 프로그램) ex)ISAP 2018 http://34.68.56.250/project/isap2018/default.php

2019년 초 (서버 이전과 css 변경) ex)ICHSEA 2019  http://34.68.56.250/project/ichsea2019/default.php

2019년 후반 (basic program 완성) ex)IMID 2019  http://34.68.56.250/project/imid2019/default.php

IMID 2019 관리자 admin / admin

분과 위원장 test01 / test

분과위원장 test02 / test

# 온라인 논문 투고 시스템 행사 목록입니다. (국제 학회)

1년에 대략 10개~15개 정도의 행사를 진행하며 온라인 프로그램 개발을 담당하고 있습니다.

도메인 신청, 서버에서 도메인 연결, 프론트엔드 ~ 백엔드까지 담당하고 있습니다.

2019년도 8월에 같이 일하던 팀장님이 퇴사한 이후에는 혼자 프로젝트를 진행하고 있습니다.

또한, 행사장에 가게 되면 행사장에서 참가자들 정보를 확인하고 네임택을 나눠주는 작업을 하는데

이 작업을 하기 위해서 VB6로 ERS 프로그램을 제작하기도 했었습니다. 

주 내용이 아니기에 [ERS](#ERS)에서 설명하겠습니다.

# 시스템 절차

온라인 논문 투고 프로그램으로

1. [회원 가입](#회원가입)
2. [논문 투고](#논문투고)
3. [등록](#등록)
4. [심사](#심사)
5. [분과 이관 신청](#분과이관신청)
6. [분과 이관 결정](#분과이관결정)
7. [기타페이지](#기타페이지)
8. [관리자](#관리자) 
9. [시스템변천사](#시스템변천사) 
10. [특이사항](#특이사항) 
11. [어려웠던점](#어려웠던점) 

기타에는 추가적인 프로그램으로 매 행사마다 들어가는 내용은 아니고 가끔 들어가는 내용입니다.

논문을 투고하고 2차로 Full Paper를 제출할 때, 아니면 늦게 제출하는 사람들을 위한 Late Paper도 있고

그 행사에서만 개최하는 특정 어워드를 위한 프로그램(사진 제출), 학생 전용 논문 투고 등등입니다.

# 회원가입

회원 가입은 기본적인 회원 폼인데, 특이 사항은 참가자들의 정보(초청연사나 단체 기관들)를

한번에 받아서 엑셀로 작업하여 그 부분을 데이터베이스에 맡게 조작하여 query문으로

데이터를 밀어넣는 경우가 많았습니다.

# 논문투고

논문 투고는 교신저자의 정보, 발표자의 정보, 논문 제목, 논문 abstract, 논문 발표 타입,

키워드, 저자들 정보, 파일 업로드 등등으로 구성 되었습니다.

논문 제목과 논문 abstract를 저장하는 부분은 ckeditor를 사용하고 있습니다.

# 등록 

등록 시스템은 행사마다 제공하는 프로그램이 조금씩 달라 매번 다르게 구성 되고,

원하는 PG사도 달라서 행사마다 다르게 진행 됐습니다. 

페이게이트, 이니시스, 올앳페이, 더존페이, 엑심베이 등등

결제를 USD와 KRW로 나눠서 받아야 했기 때문에(대부분 국제 학회),

보통 한 행사에 두 개의 PG사를 사용 했습니다.

현재는 엑심베이(USD), 더존페이(KRW)로 많이 사용하고 있습니다.

등록하는 폼에서 주로 추가되는 내용은 

1. 등록 기간 분류(사전, 현장 or 사전, 정규, 현장)

2. 학생 일반 분류(학생, 일반)

3. 멤버 논멤버 분류 (member(kids,sdi,일반 멤버) , non-member)

4. Additional Item 추가 여부(동반자에 따른 내용 ( 동반자 수, 이름 ), Banquet 개수, USB 개수)

5. Tour 추가 여부 (경주에서 행사할 경우 경주에서 유명한 관광지 Tour, 대전일 경우 대전에서 유명한 관광지)

   보통 2~4가지의 경우로 나뉘어서 선택 했습니다.

6. Hotel 추가 여부 ( 행사장 근처의 호텔들을 선택할 수 있게 데이터베이스에 미리 저장 )

7. 등록이 완료 되면 PDF로 Invoice 생성하고, 결제가 완료 되면 PDF로 Receipt 생성하고

   결제 완료 메일이 나갑니다. PDF는 tcpdf를 사용했습니다.

# 심사

심사는 투고한 논문을 각 분과의 심사위원 or 분과위원장이 심사하게 됩니다. 

이 심사위원이나 분과위원장은 관리자 페이지에서 관리자가 부여할 수 있습니다.

심사는 심사폼을 따로 구축하여 심사하는 경우와 리스트에 간단하게 셀렉트 박스로 구축해서 작성하는 경우가 있었습니다.

# 분과이관신청

분과 이관 신청은 각 분과의 분과위원장이 신청하게 되는데, 해당 논문이 이 분과에 적합하지 않다고 생각했을 경우

다른 분과를 선택하고 그 분과에 적합한 이유를 적으면 다른 분과위원장에게 메일이 가는 형태로 구축 되었습니다.

# 분과이관결과

분과 이관 신청이 왔을 경우 해당 분과의 분과위원장이 이관을 수락할지 거절할지를 선택하게 되는 페이지입니다.

# 기타

이 부분은 요청하는 형식이 다 달라서 정형화 되어 있지 않았습니다.

사진을 제출하는 페이지, 학생증과 기타 정보를 제출하는 페이지, Late Paper 제출 페이지, Full Paper 제출 페이지 등등

필요한 여러가지 페이지를 제작 했습니다.

# 관리자

관리자 페이지는 회원 정보와 논문 투고 정보, 등록 정보등 입력한 형태를 확인할 수 있게

구성되어 있고 수정, 삭제할 수 있습니다. 엑셀로 다운 받을 수 있습니다.

회원 정보에서는 참가자의 권한을 설정할 수 있고, 논문 투고는 논문 투고한 파일을 전체 다운받을 수 있고

등록 정보에서는 결제 확인 메일을 보내는 등의 기능을 가지고 있습니다.

# ERS

행사장에서 사용하는 프로그램으로 VB6로 제작합니다.

기능은 참가자들의 등록정보를 받을 수 있는 폼과 리스트로 구성되어 있었고,  

네임택, 영수증, 참가확인증을 프린트하는 내용이 있었습니다.

참가자들이 온라인으로 등록한 정보에 기획팀 직원분이 현장에서 필요한 정보를 

Excel파일에 추가해서 저에게 전달하면 행사장에서 사용하는 데이터베이스에 이 정보를 저장하고 

이 데이터를 엑셀로 동기화하여 엑셀에서 하루 입장 통계, 정산을 내는 작업까지 진행 하였습니다.

# 시스템변천사

2018년도의 시스템은 validation을 javascript에서 form 자체를 받아 그 안에서 검사하는 방식을 사용했습니다.

http사이트로 구축 되었으며 순수하게 javascript와 php만으로 구성 된 홈페이지였습니다.

2018년 (입사 시 프로그램) ex)ISAP 2018 http://34.68.56.250/project/isap2018/default.php

2019년 초 (서버 이전과 css 변경) ex)ICHSEA 2019  http://34.68.56.250/project/ichsea2019/default.php

2019년 후반 (basic program 완성) ex)IMID 2019  http://34.68.56.250/project/imid2019/default.php

IMID 2019 관리자 admin / admin

분과 위원장 test01 / test

분과위원장 test02 / test

현재 - laravel 과 vue.js를 사용한 spa형태로 논문 투고프로그램을 새로 구축해볼까 하여

혼자 homestead 환경에서 작업하고 있습니다. 

# 특이사항

Re19와 icwe2019 같은 경우는 홈페이지를 처음에 회원가입 + 등록으로 구축을 했다가

등록만 할건데 회원가입을 왜 하냐는 조직위원들의 불만 사항이 있어서 등록폼에

아이디와 패스워드를 같이 공유하느라 시스템을 변경하고

이렇게 되면서 등록 화면을 나타낼 때 회원가입 할 때 설정했던 나라를 바탕으로

KRW인지 USD인지 구분하는데 이 부분이 안 되어

페이지를 나눠서 구분했습니다. 현재라면 json으로 USD와 KRW를 변경할 수 있을 것 같기도 합니다.

Wta2019는 국제 무역학회로 전시장이 큰 행사였습니다.

논문 투고 시스템이 아닌 참가자들끼리 미팅을 주선하기 위한 미팅 프로그램을 만들었습니다. 

회원 가입을 하고 buyer 정보를 입력하고 원하는 미팅 시간을 선택하면 

관리자는 참가자들이 신청한 미팅 시간을 보고 조절하여 상담을 잡아주는 프로그램입니다.

참가자들끼리 신청하면 무분별하게 진행 될 수 있다고 이렇게 조절했습니다. 

imid2020online 현재 진행하고 있는 행사인데, 외주쪽에 행사를 맡겼는데

컨퍼런스가 온라인으로 진행 된다하여 외주쪽에 맡기면 돈이 너무 많이 들 것 같고

일정이 촉박할 것 같다며 행사를 다시 가져와서

참가자들의 정보와 논문 정보를 다 엑셀로 정리해서 다시 재 가공하여 밀어넣는 작업을 진행했습니다.

회원가입도 논문투고도 없고 동영상 올리는 부분만 존재하고,

나머지는 데이터베이스를 구축하여 모든 정보를 다 엑셀로 받아

일일이 업데이트 했습니다.

동영상을 업로드하고 참가자들만 동영상을 볼 수 있게 진행하고 있습니다.

이 부분을 진행하기 위해 카테노이드라는 업체와 협업하였으며,

동영상을 업로드하고 콜백을 받아 처리해야 할 부분이 많아서

(업로드, 암호화, 디지털 워터마킹, 키 값 받아서 연동, 미리보기 구현, 인트로 아웃트로 영상 삽입 등)

카테노이드라는 업체에게 자문을 많이 구하여 해결 했습니다.

카테노이드라는 업체는 kollus라는 영상 플랫폼을 가지고 있는 업체입니다.

# 어려웠던점

그 외에는 대부분 논문 투고 시스템이고 어려운 점은 처음 해보는 일들이 많고

해야 하는 일들이 다양해서 어려움을 많이 겪었던 것 같습니다.

서버가 두 개로 운영 되는데(cy-mice,web-geni) 같은 버전으로 운영 되는 게 아니다 보니

한쪽 버전이 낮아서 같은 소스가 안 먹는 경우도 발생하는 등 버전 관리에 여러 어려움이 있었습니다.

SSL을 신청하여 cy-mice서버에 설치하는데 서버에 어떻게 설치해야 하는지 몰라서 어려움을 겪기도하고,

메일이 안 간다하여 SPF도 등록했는데도 잘 가지 않는 현상도 있고

web-geni서버에도 SSL을 신청해서 서버에 설치하는데, web-geni는 IP를 도메인만 다르게하여 보여주는 홈페이지 형식이라

각 도메인마다 SSL을 적용하려면 멀티 도메인을 처음부터 신청해야 해서 단일 도메인을 신청했다가 다른 사이트가 추가 되면서

멀티 도메인으로 변경하는 해프닝도 있었고, 이 부분도 또한 설치하는 데 어려움이 있었습니다.

web-geni서버는 SPF를 신청하고 sendmail.cf나 httpd.conf 부분을 수정해도 정상적으로 메일이 안 가는 경우가 있었습니다.

IDC에서 메일 서버도 같이 운영하는데, 직원들 메일 계정 생성도 해주고 비밀번호 까먹으면 알려주고

예전 행사도 아직 계약중이면 비밀번호 까먹으면 알려주고 새로운 직원 들어오면 IP 할당해주고 하루에도 몇 번씩 엑셀로 데이터 새로 받아서 

서버에 밀어넣는 경우도 많고 행사장 가서도 IP 설정하고 로컬 네트워크에 mysql 권한을 부여해주고 

vb6로 setup한 ERS프로그램 내용 수정되거나 새로운 내용 추가 되면 새로 setup해서 exe파일 공유 폴더로 다 넘겨서 실행 다시 해주고

손이 많이 가는 업무를 해왔습니다.

아무래도 프로그램 개발을 하는 사람이 혼자이다 보니 업무에 대한 고충을 토로할 사람이나 보고 배울 멘토가 없는 게 어려운 것 같습니다.

중간중간에 급하게 협업 했던 경우가 있는데 그럴 때마다 다른 사람들이 일하는 내용에 대해 접하게 되어 성장할 기회가 생기는 것 같습니다.

1월 초에 imid2020이라는 행사를 외주로 맡기면서 이 행사는 스프링으로 제작이 되었는데, 이 부분에 대해서 어떻게 제작 되는지 볼 기회가 생겼었습니다.

외주 하시는 분이 텍스트 같은 부분은 급하면 저에게 수정 하라면서 eclipse에서 회원가입에 대한 crud 부분을 한시간 가량으로 보여주셨었는데, 

이 기회를 통해 framework의 동작 구조나 이런부분에 대해 흥미가 많이 생겨서 그 이후로 시간이 날 때마다 laravel을 공부하고 있습니다.

laravel + vue.js로 논문 투고 시스템이 제작되면 githup에 업데이트 하겠습니다.

여기까지 읽어 주셔서 감사합니다.

