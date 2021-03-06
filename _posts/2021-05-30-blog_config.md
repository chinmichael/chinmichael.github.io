---
title: "[Blog Making] _config.yml 설정 (프로필 등)"
excerpt: ""

categories: 
    - Blog Making
tags:
    - [Blog, Github Pages]

toc: true
toc_label: "목차"
toc_icon: "indent"
toc_sticky: true

date: 2021-05-30
last_modified_at: 2021-05-31
---
<br/>

오늘 포스팅에서는 저번에 잠시 언급한 마크다운 문법과 포스팅 방법에 대해 이야기하기 전 `_config.yml` 파일을 수정하여 프로필 등 <u>기본적인 블로그 설정을 하는 법</u>에 대해 간단히 말씀드리겠습니다.
<br/><br/>

이번 포스팅에서는 제 블로그를 기준으로 프로필, SNS링크, 스킨 등 간단한 설정에 대해서만 설명해 드리고 댓글 기능 등의 부분에 대해서 추후 기능 추가 포스팅을 할때 `_config.yml` 설정도 함께 다루겠습니다.
<br/><br/>

주의하실 점은 `_config.yml`의 환경설정과 변수들은 사이트가 빌드 될 때 한번만 읽어들이기 때문에 변경사항을 로컬에서 확인하기 위해서는 서비스를 종료하고 `bundle exec jekyll serve`를 다시 실행시킬 필요가 있습니다.
<br/><br/>

이 포스팅의 경우 추가할 내용이 생기면 업데이트 하도록 하겠습니다.   
테마에 기본제공되는 [Quick-Start Guide](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/) 문서를 참고하셔도 좋습니다.
<br/><br/>

## 1. Skin & Site Setting
<u>Minimal Mistakes 테마의 기본 제공 스킨, 언어, 블로그 이름, 댓글, 검색 기능 등을 설</u>정하는 부분입니다. 현재 제 블로그에서 변경한 부분은 다음과 같습니다.
```
minimal_mistakes_skin    : "dark"

# Site Settings
locale                   : "en-US"
title                    : "Lemon Code Memo"
title_separator          : 
subtitle                 : "레몬쿠키's Blog"
name                     : "레몬쿠키 코드 메모장"
...
url                      : "https://chinmichael.github.io"
...
repository               : "chinmichael/blog_comments"

...

logo                     : "/assets/images/android-chrome-192x192.png"

...
comments:
    provider               : "utterances"
    ...
    utterances:
    theme                : "photon-dark" # "github-light" (default), "github-dark"
    issue_term           : "pathname" # "pathname" (default)
    ...
...

search                   : true # true, false (default)
search_full_content      : true # true, false (default)
search_provider          : lunr # lunr (default), algolia, google

``` 

<br/>

바꾸시기 전 <u>기존 설정은 `#`을 통해 주석처리</u> 해놓으시는 편이 나중에 되돌리실 때 좋습니다. 대체로 옵션명들은 추측이 가능하게 짜여있습니다. 몇가지 추가 설명을 드리면
<br/><br/>

***
`repository`와 `comments` 관련 부분은 댓글기능에 대한 부분입니다. 위에서 말씀드린대로 댓글 기능 추가 포스팅을 할 때 다시 설명드리도록 하겠습니다.

<br/>

***
`locale`의 경우 프로젝트 루트 폴더 중 `_data`폴더 내의 `ui-text.yml`에 <u>설정되어 있는 언어설정</u>을 불러 사용할 수 있습니다. 한국어 설정도 있기 때문에 만약 사용하시려면 `locale`의 `en-US`를 `ko`로 바꿔 입력하시면 됩니다. 이로 인해 바뀌는 메뉴이름(최신글, 태그 등)들을 세세하게 바꾸시려면 `ui-text.yml`의 각 메뉴명 설정을 바꾸시면 됩니다.

<br/>

***
`title`, `subtitle`, `url`, `logo` 등은 상단 블로그명에 해당하는 설정을 변경할 수 있습니다. `logo`는 프로젝트 폴더 내에 저장한 이미지를 불러와서 사용하면 되는데, 되도록 <u>이런 첨부파일은 `assets` 폴더에 정리하여 저장하는 편이 좋습니다.</u> 저는 `assets` 폴더 내에 `images`폴더를 추가하여 로고, 프로필 사진 등을 저장했습니다.

<br/>

***
`search`에 해당하는 설정을 위와 같이 해두시면 테마에 기본적으로 내장된 검색 기능을 활성화 할 수 있습니다. (블로그 상단에 검색 아이콘이 생깁니다.)   
이에 관련된 세부사항은 나중에 공부하게 되면 따로 포스팅을 하던가 이 글에 추가하도록 하겠습니다.

<br/>

***
`skin`은 테마에서 초기에 기본적으로 제공하는 [Quick-Start Guide](https://mmistakes.github.io/minimal-mistakes/docs/configuration/)에서 미리 볼 수 있습니다.

<br/>

`skin`의 세부적인 색상은 `_sass` 폴더 내 _sass/minimal-mistakes/skins 에서 각 해당 스킨 파일을 조정함으로서 변경할 수 있습니다. 주로 강조 색상의 경우 `$primary-color` 부분을 변경하면 나머지 부분들이 적당히 블랜딩 되어 바뀌게 기본 설정 되어 있습니다. 저 같은 경우  `dark` 스킨에서 `$primary-color`를 `#facc2e`로 바꾸기만 했습니다.

<br/>

추가적인 개인 Tip으로 블로그의 <u>CSS를 수정할 때는 전체적인 조화와 코드 유지보수성을 위하여</u> 텍스트 등의 색상 설정은 다음과 같이 위 <u>스킨의 색상 변수명을 이용</u>해주시면 좋습니다. (블로그 CSS 수정 Tip은 추후 간단히 포스팅하도록 하겠습니다.)
```css
.page_title {
    color: $primary-color;
}
```

<br/><br/>

## 2. Site Author(프로필) & Site Footer
블로그 사이드바의 프로필 부분 그리고 하단 footer 부분을 설정하는 부분입니다.   
저는 메일과 Github 정도의 링크만 걸었지만 여타 SNS 등의 링크를 공개하실 분은 마찬가지의 방법으로 주석을 해제하고 설정하시면됩니다.
```
# Site Author
author:
  name             : "다올이형 레몬쿠키"
  avatar           : "/assets/images/bio.jpg"
  bio              : "블로그 준비중<br/>日日新 又日新"
  location         : 
  email            :
  links:
    - label: "Email"
      icon: "fas fa-fw fa-envelope-square"
      url: mailto:chinmichael@naver.com
    ...
    - label: "GitHub"
      icon: "fab fa-fw fa-github"
      url: "https://github.com/chinmichael"
    ...

# Site Footer
footer:
  links:
    ...
    - label: "GitHub"
      icon: "fab fa-fw fa-github"
      url: "https://github.com/chinmichael"
    ...
```

<br/>

마찬가지로 굉장히 직관적이기 때문에 천천히 읽어나가면 수정이 그리 크게 어렵지 않다고 생각합니다. `avatar`은 경우 위 `site setting`의 `logo`처럼 `assets`에 가져온 이미지 파일의 상대주소를 입력했습니다.
<br/><br/>

`bio` (프로필 소개) 부분에서 줄바꿈이 필요하신 경우 HTML의 `<br/>`태그를 사용하시면 됩니다. <u>물론 Markdown문법의 강조 표현을 넣으실 수도 있습니다.</u> 마크 다운 문법에 대해서는 다음 포스팅에서 다뤄보도록 하겠습니다.

<br/><br/>

## 3. Defaults
```
# Defaults
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      show_date: true
      read_time: #true
      comments:  true
      share: true
      related: true
  # _pages
  - scope:
      path: ""
      type: pages
    values:
      layout: single
      author_profile: true
```

<br/>

포스팅 화면(`_posts`)과 카테고리나 태그 메뉴 등 Minimal Mistakes테마의 archive 페이지(`_pages`)의 <u>레이아웃 종류 등의  기본값을 설정</u>하는 부분입니다. 예를 들어 `author_profile`은 좌측의 프로필 부분(모바일에서는 상단)을 보이게 하는가에 대한 부분입니다.

<br/>

***
[하우투 시리즈](https://devinlife.com/howto%20github%20pages/blog-config/)를 참고하여 `_posts`와 `_page`에 대해 좀 더 자세히 설명해 드리면,   
우선 Jekyll에서 게시물은 기본적으로 `post`와 `page`로 구분됩니다.
<br/>

`_posts`폴더에 속한 `post`들은 날짜를 기반으로 파일명이 작성되며 뒤에서 다룰 포스팅 파일들이 됩니다.   
`_pages`폴더에 속한 `page`들은 사이트맵, 카테고리, 소개페이지 등 날짜와 관계없이 특정 주소로 보여줄 파일들입니다.
<br/>

뒤에서 다시 다뤄지겠지만 위 `post`와 `page`파일들은 보통 확장자가 `.md`인 <u>Markdown파일로 작성되며 Jekyll이 해석하여 HTML로 변환해 게시</u>합니다.
<br/>

이때, <u>Markdown파일 최상단에는 제목, 레이아웃, 카테고리 등을 지정하기 위한 YFM(YAML Front Matter)이란 포맷</u>을 위치시킬 수 있는데, 위 `default`의 설정에서는 해당 YFM 포맷에서 공통으로 적용시킬 기본값을 세팅할 수 있습니다.

<br/>

***
 그밖에는 우선 댓글기능을 위해 `comment`부분을 활성화하고 `read_time`대신 `show_date`를 활성화하여 포스팅 날짜를 표시한 정도지만...... 혹시 모르니 이 부분은 수정하지 않은 부분에 대해서 생략을 하지 않았습니다. 

<br/>

언제나 읽어주셔서 감사합니다.^^  

***

```
개인 공부용 블로그입니다.
잘못된 부분에 언제든지 댓글이나 메일로 지적해주시면 감사하겠습니다.
```
