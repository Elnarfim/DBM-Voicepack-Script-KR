# DBM 음성팩 제작 가이드 (Voice version 13 / toc version 100005)

## 1. 준비물

마이크, 녹음 프로그램(윈도 내장 녹음기도 가능), ogg 변환 프로그램, 노멀라이저 프로그램, 텍스트파일 에디터(메모장 가능)

마이크가 없는 분들은 폰의 녹음기로도 가능합니다.

음성 파일 편집 프로그램은 ogg 파일 포맷을 불러들일 수 있어야 합니다.

유명한 무료 프로그램으론 ocenaudio와 audacity가 있습니다. 개인적으로 전 ocenaudio를 추천합니다. https://www.ocenaudio.com/

## 2. 녹음하기

github의 음성 스크립트 파일을 받아서 대본대로 녹음을 하면 됩니다. 대본과 100% 일치하게 녹음할 필요는 없습니다. 적당히 자기 스타일에 맞게 고쳐서 하세요.

녹음할때 음질 스펙은 크게 높지 않아도 상관없습니다. 가장 일반적인 음원 스펙인 128kbps 혹은 192kbps에 44100Hz 스테레오로 녹음하면 됩니다.

녹음파일 포맷은 어느거로 해도 상관은 없는데 ogg 포맷을 사용하므로 ogg로 바로 하면 편합니다. ogg 퀄리티는 3 정도가 적당합니다.

## 3. 변환 및 볼륨 조절

녹음이 끝났으면 ogg 파일로 변환하십시오. 위에 소개한 무료 프로그램 등을 사용해서 퀄리티 3이나 4에 맞춰놓고 일괄 변환하시면 됩니다. 

변환이 끝나면 볼륨 조절을 해야 합니다. 볼륨 조절은 음성팩 제작에서 가장 중요한 부분으로, 실제 게임상에서 적절하게 음성이 들려야 하기 때문입니다. 위에 언급한 노멀라이저 프로그램중 하나를 사용해서 변환된 ogg 파일을 불러서 볼륨을 조절하십시오.

변환하기 전의 파일은 볼륨을 맞춰봐야 ogg로 변환할 때 어떻게 볼륨이 바뀌게 될지 알 수 없습니다. 설정한 상태에 따라 결과물이 다르기 때문에 최종적으로 ogg 파일에다가 볼륨을 맞추시는게 중요합니다. 볼륨 조정은 gain값과 normalize 값을 바꿔가며 맞추셔야 합니다. ocenaudio 기준 음성 파형이 바의 천장까지 도달해야 게임상에서 적절한 볼륨이 나오니 참고하세요.

## 4. toc 제작 및 패키징

음성팩을 와우가 인식하게 하려면 toc 파일을 만들고 완성한 음성파일들을 폴더에 맞게 배치해야 합니다

먼저 와우의 AddOns 폴더 안에 들어갈 애드온 폴더부터 만들어야 하는데, 폴더 이름은 <b?반드시 DBM-VP가 앞에 붙고 그 다음에 음성팩 이름이 들어가야 합니다.</b>

함서로 음성팩의 예를 들면 DBM-VPHamseoroKR 로 되어있죠. HamseoroKR이 애드온 이름이 되는겁니다

<b>애드온 이름을 지으실때 KR을 반드시 붙일 필요는 없습니다.</b> 영문으로 음성팩 이름을 지어서 폴더를 만드세요.

풀링 카운트 음성 파일은 폴더 안에 count 폴더를 만들어서 넣어야 합니다. <b>소문자로 만드세요</b>

또다른 서브 폴더로는 Thogar가 있습니다. 이건 드군 레이드 중에 기차 지나다니는 네임드용 음성인데 안만들어도 상관없습니다.

폴더명은 마찬가지로 대소문자를 맞춰서 작성해야 합니다.

이제 메모장이나 Editplus 같은 파일 에디터를 열고 toc 파일을 만들면 됩니다.

까마귀의눈 음성팩 toc를 예시로 설명하겠습니다.

```
## Interface: 70200
## X-Min-Interface: 70200
## Title:|cffffe00a<|r|cffff7d0aDBM|r|cffffe00a>|r |cff69ccf0Voicepack Eye of Crow|r
## Title-koKR:|cffffe00a<|r|cffff7d0aDBM|r|cffffe00a>|r |cff69ccf0음성팩 까마귀의눈@헬스크림|r
## DefaultState: enabled
## RequiredDeps: DBM-Core
## Author: Elnarfim
## Version: 0.7
## X-DBM-Voice: 1
## X-DBM-Voice-Name: 까마귀의눈 (Korean Male)
## X-DBM-Voice-ShortName: EyeofCrowKR
## X-DBM-Voice-Version: 7
## X-DBM-Voice-HasCount: 1
```

Interface - 와우 toc 버전입니다. 10.0.0은 100000 / 리분 클래식은 30400 입니다. 패치가 나오면 toc 버전이 올라갈 수 있으니 주기적으로 toc 버전 확인 필요

X-Min-Interface - toc 버전과 동일하게 적으면 됩니다

Title - 영문 클라용 애드온 이름입니다. 캐릭터 선택 화면에서 애드온 버튼 누르면 나오는 목록에 표시될 이름입니다
앞에 색깔 코드가 씌워져있는 |cffffe00a<|r|cffff7d0aDBM|r|cffffe00a>|r 블럭은 건드리지 마시고 그 다음 블럭의 Voicepack 뒤부터 |r 사이에 이름을 쓰면 됩니다

Title-koKR - 한글 클라에서 보일 이름입니다. 영문 타이틀과 똑같은 위치에 한글명을 쓰면 됩니다.

DefaultState - 기본적으로 애드온 목록에서 체크되어 있게 하는 옵션입니다. enabled로 설정하세요

RequireDeps - 다른 애드온에게 의존성을 갖게 하는 옵션입니다. DBM-Core로 쓰시면 됩니다

Author - 제작자 이름입니다. toc파일은 언어 코드가 붙은 옵션 외에는 가급적 영어로 작성하셔야 합니다. 이것도 가급적 영어로 작성해주세요

Version - 음성팩의 자체 버전입니다. 0.1로 하든 1.0으로 하든 자기 스타일대로 버전 넘버 지어주세요

X-DBM-Voice - 1로 설정하세요

X-DBM-Voice-Name - DBM 옵션에서 음성팩을 선택할 때 보이는 이름입니다. 가급적 영문 제목을 쓰는게 좋겠지만 부득이한 경우 한글로 쓰셔도 무방합니다. 음성팩 이름 뒤에는 괄호 치고 위처럼 언어와 성별을 영문으로 추가하는걸 권장합니다

X-DBM-VoiceShortName - 반드시 <b>음성팩 폴더명에서 앞에 DBM-VP를 뺀 나머지 부분을 입력해야 합니다</b>

X-DBM-Voice-Version - DBM 음성팩 버전 번호이며 DBM 업데이트에 따라 버전 넘버가 조금씩 올라갑니다. 용군단 사전 패치인 현재 12로 되어 있습니다. 보이스 버전 넘버는 본 가이드의 맨 윗줄에 명시되어 있으므로 주기적으로 이곳을 방문해서 확인하면 됩니다. 더 빨리 알고 싶다면 커스의 DBM Voicepack Demo (https://www.curseforge.com/wow/addons/dbm-voicepack-demo) 최신 알파 버전을 받아서 toc 파일을 열어보면 됩니다. <b>버전 번호가 DBM과 맞지 않으면 음성팩이 로딩되질 않으니 주의하세요</b>

X-DBM-Voice-HasCount - 카운트용 음성이 들어있을때 1로 하시고 없으면 0으로 하십시오. 카운트 음성을 빼놓고 만드는 경우는 없으니까 1로 하면 됩니다

## 5. 클래식 버전
위의 toc 파일에는 리테일과 클래식 중 하나의 toc 버전만 사용할 수 있습니다. 만약 리테일과 클래식 통합 보이스팩을 제작하고 싶다면 클래식 버전별 멀티 toc 파일을 작성해야 합니다

```
DBM-VP보이스팩이름.toc - 기본값 toc입니다. 최신 확장팩 toc 버전이 들어가야 합니다
DBM-VP보이스팩이름_Mainline.toc - 최신 확장팩 toc 버전이 들어갑니다
DBM-VP보이스팩이름_Vanilla.toc - 오리지날 클래식 (시대 서버) toc 버전이 들어가야 합니다
DBM-VP보이스팩이름_TBC.toc - 불성 클래식 toc 버전이 들어가야 합니다
DBM-VP보이스팩이름_Wrath.toc - 리분 클래식 toc 버전이 들어가야 합니다
```

기본값 toc에는 Interface 항목 아래에 다음의 내용이 들어가야 합니다
```
## X-Min-Interface: 100000 - 최신 확장팩 toc 버전
## X-Min-Interface-Classic: 11403 - 클래식 시대섭 toc 버전
## X-Min-Interface-BCC: 20504 - 불성 클래식 toc 버전
## X-Min-Interface-Wrath: 30400 - 리분 클래식 toc 버전
```

기본값 toc와 Mainline은 반드시 들어가야 하며 지원할 클래식 버전 toc를 추가로 제작하면 됩니다. 내용은 4번의 toc 양식과 동일하게 작성하면 됩니다.

## 6. 제작 완료

작성이 끝나면 반드시 UTF-8 형식으로 toc 파일을 저장하세요. UTF-8로 저장하지 않으면 애드온 목록에서 ???? 로 뜨게 되니 주의하세요. <b>저장할 파일명은 폴더이름과 같아야 합니다.</b> 까마귀의눈을 예로 들면 DBM-VPEyeofCrowKR.toc 가 되야 합니다. 폴더명의 대소문자와 맞춰야 하고 폴더나 파일 이름에 <b>한글을 쓰면 안됩니다.</b>

toc 파일은 음성팩 폴더 안에 넣으면 되는데 스크립트에 없는 음성 파일 3개가 더 필요합니다. 마린 고고고 효과음과 띠 띠 하는 비프음인데 위의 3가지 ogg 파일을 받아서 음성팩 폴더안에 넣으면 됩니다.

작성이 끝났으면 이제 와우를 실행해서 애드온이 잘 등록되어 있는지 확인 후 DBM 옵션에서 음성팩을 선택해서 카운트부터 테스트하시기 바랍니다. /pull 5 쳐서 녹음한 음성이 잘 나오는지 검사한 다음 던전이나 레이드를 돌면서 전체적인 테스트를 해보세요. 볼륨이 적당한지 명확하게 들리는지 여부를 점검한 후 이상이 없으면 압축해서 인벤이나 커스 등에 올리면 됩니다.
