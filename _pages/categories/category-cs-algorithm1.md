---
title: "Algorithm Basic"
layout: archive
permalink: categories/algorithm-basic
author_profile: true

sidebar_navi: true
---
***
기본적으로 [알고리즘 도감](https://play.google.com/store/apps/details?id=wiki.algorithm.algorithms&hl=ko&gl=US)(책)을 바탕으로 요약 및 개인적으로 내용을 추가해 정리합니다.   
위 앱의 애니메이션을 참고하시며 공부하시면 더 도움이 되실거라 생각합니다. (광고 X)   
여느 포스팅처럼 공부 도중 추가할 내용이 생기면 업데이트 하도록 하겠습니다. (코드구현은 별도 카테고리)   
{: .notice--primary}

{% assign posts = site.categories['Algorithm Basic'] %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}