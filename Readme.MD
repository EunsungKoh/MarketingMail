# Email Marketing
- This repository is made for advertising [Deepbio](http://www.deepbio.co.kr) by Email.
- [해당 사이트](https://webdesign.tutsplus.com/ko/articles/build-an-html-email-template-from-scratch--webdesign-12770)를 참고로 제작하였습니다.
- Email Marketing의 특성상 HTML을 사용하지만 일부 제약 조건이 발생합니다. 

  (HTML의 헤더부터 사용하지 않고 Body 부분만을 강제적으로 메일의 내용에 삽입하여 사용합니다.)
  - div 태그를 사용할 수 없습니다.
      - 정확히 말하자면 사용이 불가능하지는 않으나, 일부 브라우져에서는 작동하지 않아 의도하지 않은 layout으로 변형될 소지가 존재합니다.    
      - [W3C Validator](http://validator.w3.org/)와 [litmus](https://litmus.com/)를 통해서 확인 가능합니다.    
          - litmus는 trial 기본적으로는 유료입니다.      
      - div의 사용이 불가하기 때문에 모든 구조는 table로 구성되어 있습니다.
          - debugging 및 테스트를 위해서는 border="0"으로 설정되어있는 값을 border="1"로 설정하면 전체적인 윤곽을 확인하며 작업할 수 있어 편리합니다.
  - font 사용에 제약이 존재합니다.
      - 해당 코드에서는 HTML에서 기본적으로 제공하지 않는, Open-Sans를 사용하였습니다. Open-Sans는 작동했지만, 다른 font가 이상없이 작동할 것이라고 보장할 수 없습니다.
- 다양한 환경에 대한 테스팅이 필요합니다.
    - 앞서 말했던 litmus를 이용한다면 수월히 확인이 가능하지만, 해당 사이트를 조사하지 않는다면 직접적으로 확인해봐야합니다.
        - 일반적인 웹사이트를 통해 메일을 조회할 경우에는 크게 문제가 생기지 않습니다.
        - 다만, 메일 엔진을 이용하여 메일을 조회할 경우에 layout이 틀어지는 문제가 발생했습니다. (Window Mail, Outlook, Apple Mail)
- Gmail을 통해서 메일을 발송하였으며, 발송법은 다음과 같습니다.
    1. 메일의 본문에 본인이 알아보기 쉬운 내용의 임의의 단어를 입력한다.
        - 저는 주로 ```*********```를 입력하였습니다.
    2. Chrome 혹은 Firefox에서 제공하는 inspection(검사) 기능을 이용하여 해당 부분을 찾습니다.
    3. 해당 부분을 우클릭하여 Edit as HTML (HTML로 편집) 버튼을 눌러 ```********```라고 명시되어 있는 내용을 수정합니다.
        1. 본문의 모든 내용을 넣지 않습니다.
        2. Body의 내용만을 넣습니다.
        3. ```********```를 Body가 시작하자마자 존재하는 table로 갈음합니다.
