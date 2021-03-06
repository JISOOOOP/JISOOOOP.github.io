---
layout: post
title:  "HTML/CSS BASIC 교육 정리"
date:   2020-01-20 18:11:00
categories: study review HTML CSS
---

# HTML / CSS BASIC

### 웹의 구성요소

- HTML : 내용의 위치에 맞게 잡아줌
- CSS : 모양과 표현 같은 것을 잡아줌(디자인을 입힌다)
- Javascript : 데이터를 가져오거나 창을 열 떄(따로 교육에서)



### 웹 제작 시 고려 사항

W3C에서 권고한 표준을 지켜 제작

- 웹 접근성
  - 물리적 또는 인적 환경에 제약이 없는 것
- 웹 호환성
  - 브라우저에 대해 호환

- 엘리먼트의 구성요소
  - 여는 태그, 어트리뷰트, 내용, 닫는 태그

- !DOCTYPE : 문서를 해석하는 방법
- html
  - lang 속성 : 웹 접근성을 준수하기 위함, 어떤 언어로 되어있는지
- head
  - meta : 문서에 대한 정보 요약, 인코딩 저자 대표이미지 사용자에게 안보임
    - 인코딩 설정 IE 호환성 ViewPort 설정 하는데 많이 쓰임
    - 각 서비스에서 만든 meta 데이터로 페이지에 대한 요약 정보를 공유할 수 있음
      - 주의사항 : 이미지 같은 경우는 절대 경로로
  - body : 실제로 사용자에게 보이는 부분
    - h1~6태그 : 제목이나 부제목을 표현
    - p : 텍스트의 단락을 표현
    - ol, li : 순서 있는 리스트(앞에 숫자 붙임)
    - ul, li : 순서가 없는 리스트(마크 다운처럼)
    - strong, em : 굵게, 기울여서 글자 표현
    - blockquote : 인용구 표현할 떄 사용
    - pre, code : 미리 지정된 서식 그대로 표현, 모노스페이스 글꼴로 표현
    - a : 하이퍼 링크를 표현 ( a href=URL)
    - img : 이미지를 넣어줌 (src=imgPath alt=이미지 깨질떄 나오는거)
    - div : 영역을 나눌 떄 사용, display 속성이 block이 됨



- Semantic Element

  - 개발자 가독성이 좋아짐

  - 검색 엔진이 논리적으로 필요한 부분을 찾기 쉬움

  - | Tag         | Role                                                         |
    | ----------- | ------------------------------------------------------------ |
    | **header**  | 문서의 헤더 부분 - 소개나 탐색을 돕는 것의 그룹              |
    | **main**    | 주요 콘텐츠가 들어가는 부분                                  |
    | **nav**     | 문서의 네비게이션 구조                                       |
    | **aside**   | 사이드에 위치하는 공간                                       |
    | **section** | 문서의 일반적인 구획, 여러 중심 내용을 감싸는 공간           |
    | **footer**  | 문서의 푸터 부분 작성자 구획, 저작권 데이터, 관련된 문서의 링크에 대한 정보 |
    | **figure**  | 문서의 멀티미디어 요소                                       |
    | **article** | 글자가 많이 들어가는 부분(그 자체로 독립적으로 구분되거나 재사용 가능한 영역) |
    | **address** | 연락처 정보 등의 부가 정보                                   |



### CSS의 기본 구조와 셀렉터

- CSS : 문서의 표현을 기술

- 셀렉터 속성 값, 스타일 선언 블럭

- 적용 방법

  - Inline : 각 태그마다 스타일을 모두 적어는 방법 (사용 x)
  - Embedded : head안에 style로 감싸서 넣음 (CSS가 많지 않을때)
  - Externel : 별도의 CSS 파일로 분리(가장 일반적인 방법)

- CSS 상속

  - 부모의 속성이 자식에게도 적용

- CSS 셀렉터

  - CSS를 적용할 요소를 지칭

  - id는 단 하나의 유니크하게

  - class 어트리뷰트는 어려게 있어도 상관x

  - CSS 셀렉터

    - 태그
    - ID : 우선 순위가 높아 자주 쓰이지 않음
    - class : class 앞에 . 붙여서 사용. 자주 쓰임
    - 속성 : []안에 속성명의 속성 바꿈
    - 자손 셀렉터 : 여러 개일때는 콤마로 구분
    - 자식 셀렉터 : header > p {} 
    - 형제 셀렉터 : +를 사용하면 자신보다 바로 뒤의 형제를 선택
    - 모든 형제를 사용 할 때는 ~을 사용 header ~ p
    - 전체 셀렉터 : 모든 엘리먼트 선택시 * 사용 (성능 안좋음)
    - 유사 클래스 셀렉터
    - 유사 엘리먼트 셀렉터
      - 가상의 요소이기에 블록 지정이 안됨

  - CSS 우선 순위

    - 우선 순위가 낮으면 무시가 됨
    - 클래스 셀렉터 > 태그 셀렉터
    - 우선 순위가 같으면 나중에 선언된 것을 사용
    - 우선 순위의 점수를 매길 수 있음. 

  - CSS 박스 모델

    - Margin, Border, Padding, Content
    - 바깥부터 안쪽 순서로
    - background-clip 속성
      - 배경의 구성요소별 설정 가능
    - box-sizing
      - 엘리먼트 크기를 어느 기준으로 할 지
      - border-box : 테두리를 기준으로 크기 지정
      - width, heigh
        - 100%는 부모의 크기만큼
      - margin
        - 한개 값 : 네 면 모두 설정
        - 두개 값 : 상하, 좌우 설정
        - 세개 값 : 상, 좌우, 밑 설정
        - 네개 값 : 위부터 시계방향으로
        - margin-top 같이 방향 지정 가능
      - padding
        - 안쪽 여백
        - margin과 같은 설정을 갖음
      - border
        - border 스타일을 주면 기본적으로 들어감
        - 두께 밑 스타일 변경 가능
        - 설정 값의 순서는 변경되도 상관x
        - margin과 같이 방향별로도 설정 가능

  - CSS display

    - 각 태그는 한 가지의 display 속성을 갖음
    - auto를 통해 가로 가운데 정렬 가능
    - inline은 상하좌우 설정이 먹히지 않음
      - center 속성을 넣어주면 가운데 정렬
      - 기본적으로 한줄에 다
    - none은 해당 요소를 화면에서 보이지 않게 함
      - hidden과는 영역을 유지해주느냐의 차이

  - CSS Flexible 박스

    - 최신 브라우저에서 모두 지원
    - 성능면에서도 렌더링 시간이 빨라짐
    - 기존과 다르게 container에 속성을 줌
    - 기본적으로 가로배치가 된다.(Row로 설정도 가능)
    - Colum을 주면 세로방향
    - flex:?를 주면 비율 만큼의 공간 차지
    - none이면 원래 지정된 공간 차지

    

- 가로 정렬과 세로 정렬

  - block과 inline의 정렬 방법이 다름
    - block : margin 속성을 이용해 정렬
    - inline : text-align 속성을 이용해 정렬
      - 글자를 꽉 채울수록 가운데로 간다.

- Flex 가로/세로 정렬

  - justify-content : flex 방향으로 정렬
    - start, center, end
  - align-items : flex와 수직 방향 정렬
    - start, center, end
  - 정가운데 배치 : 위 두 항목을 center로 설정

- Position

  - static : 위치 값 넣어줘도 안바뀜
  - relative : 원래 위치에 배치
  - absolute : relative를 가진 가장 가까운 상위 엘리먼트 기준으로 위치
  - fixed : 전체 화면에서 위 왼쪽 5px 마진

- Overflow

  - visible : 기본 값은 
  - hidden : 넘치는 값은 가려버림
  - scroll : 가로 세로 항상 스크롤 바
  - auto : 내용이 넘칠때만 스크롤

- text-overflow

  - 가장 자주 쓰이게 될 것
  - 말줄임 표시를 쓰고 싶을때 e) 안녕하....
  - overflow:hidden , white-space:nowrap 같이 설정

- z-index

  - 겹칠 때 어떤것이 가장 위에 놓일 것인지
  - 높을 수록 가장 위에
  - 벳지 만들기 ex) 메일 쌓인거 표시 할때

- 글자 크기 표현 단위

  - | 단위   | 설명                            |
    | :----- | :------------------------------ |
    | px     | 화소 단위                       |
    | em     | 부모 요소의 글자 크기 기준 배율 |
    | rem    | HTML 글자 크기 기준 배율        |
    | pt     | 글꼴에 많이 쓰임                |
    | %      | 기본 글꼴의 상대적인 크기       |
    | vw, vh | 뷰포트 기준 너비, 높이          |

    브라우저의 기본값은 12pt, 16px, 1em

- font 적용하기

  - | 속성        | 설명                 | 값                                             |
    | :---------- | :------------------- | :--------------------------------------------- |
    | font-style  | 글자 스타일          | normal \| italic \| oblique                    |
    | font-weight | 글자 굵기            | lighter \| normal \| bold \| bolder \| 1 ~ 100 |
    | font-size   | 글자 크기            | <숫자> <단위>                                  |
    | font-family | 글꼴                 | 글꼴 이름                                      |
    | line-height | 글자가 차지하는 높이 | normal \| <숫자> \| <숫자><단위>               |

  - 속성 한번에 표기 가능

  - 웹 폰트

    - 컴퓨터에 없을 경우 웹폰트를 통해서 다운 받게 할 수 있음
    - font-face에 정의 해서 사용자에게 제공 가능
    - 외부 font resource는 링크태그 혹은 import를 통해 얻기 가능

- 이미지 스프라이트

  - 많은 이미지가 사용되면 그만큼 로딩 시간이 오래걸림
  - 여러개의 이미지를 하나의 파일로 합쳐서 관리
  - 구멍은 그대로 있고 이미지를 움직인다?
  - 단점 : 여백도 포함이기 떄문에 용량이 늘어날 수 있음
  - 단점 : 다양한 해상도를 제공 불가

- 프로젝트 진행시 웹 폰트를 활용하자

  - 구글 material 아이콘 같은것
