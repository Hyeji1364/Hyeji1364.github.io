---
layout: post
title: 파이썬 크롤링
date: 2024-04-26 17:00 +0900
description: 기타 CSS 속성
image: ../assets/img/blogcss.gif
category: 
tags: 파이썬 python vscode
published: true
sitemap: true
---

## 파이썬

### Python crawling

<hr>

오늘은 파이썬을 이용해 음원사이트의 차트 100을 가져오는 것을 실행해보겠습니다. 파이썬으로 크롤링할 예정입니다.
먼저 크롤링(crawling)이란 무엇인지에 대해 알아보겠습니다.
웹 크롤러라고 불리는 자동화된 소프트웨어가 인터넷 상의 웹사이트들을 방문하여 정보를 수집하는 과정을 말합니다.
이 과정은 주로 검색 엔진이 웹의 방대한 자료를 인덱싱하여 사용자의 검색 쿼리에 대응할 수 있는 데이터베이스를 만들기 위해 사용됩니다.

크롤링은 정보의 구조화된 수집을 가능하게 하여 데이터 분석, 검색 엔진 최적화(SEO), 시장 조사 등 다양한 분야에서 활용됩니다.

파이썬 크롤링은 웹페이지의 HTML 소스를 분석하고 필요한 정보를 추출하여 구조화된 데이터로 변환하는 기술입니다.

파이썬은 웹 크롤링을 위한 다양한 라이브러리와 도구를 제공하여 이 과정을 비교적 쉽게 만들어줍니다.

파이썬의 실행부터 음원 사이트의 top100을 json파일로 가져오는 과정에 대해 알아보겠습니다.

> #### 📍 파이썬 시작 전 준비사항

먼저, [파이썬 공식 홈페이지](https://www.python.org/downloads/)에서 파이썬을 다운로드 및 설치합니다.
vscode에서 python 확장 프로그램을 설치합니다.
<br>
![image](https://github.com/Hyeji1364/Hyeji1364/assets/161557112/a15aac9d-e4bb-4ce7-8441-04eec31956a5)

파이썬이 잘 설치되었는지를 알아보려면, terminal을 통해 확인합니다.

✅ 윈도우는 python에 3를 붙이지 않고 실행 <br>
✅ 맥은 python에 3를 붙여 실행 ! 

window :
````
python --version
````

mac:
````
python3 --version
````
<br>
파이썬 웹 크롤링에 사용되는 주요 라이브러리를 설치합니다.

#### requests
````python
    pip install requests
    pip install beautifulsoup4
    pip install lxml
    pip install pandas
    pip install selenium
````

### 파이썬에서 결과 확인방법
````python
print()
````

> #### 📍 크롤링 과정

1️⃣ 타겟 웹사이트 접속 <br>
원하는 데이터가 있는 웹사이트에 접속합니다.

2️⃣ 데이터 추출 <br>
HTML문서에서 필요한 데이터를 추출합니다. 이는 특정 태그나 속성을 기반으로 이루어질 수 있습니다.

3️⃣ 데이터 정리 및 저장 <br>
추출된 데이터를 필요에 따라 정리하고, 데이터베이스, 파일 등에 저장합니다.

<hr>

저는 벅스 차트 top100을 가져오는 것을 예제로 들어보겠습니다.
(제가 기존에 음원 스트리밍을 하는 사이트이기도 합니다😉)

벅스차트에 접속하고 순위, 곡, 아티스트 순으로 태그를 찾아줍니다.
마우스 우클릭으로 검사에 들어간 후, 각각의 요소에 마우스오버하여 태그를 찾아줍니다.

순위 :<br>

사진은 확대하면 잘보입니다.<br>

![image](https://github.com/Hyeji1364/Hyeji1364/assets/161557112/193888a9-98b2-406c-a7ce-7203cc552e4a)

▶ 순위는 'ranking > strong'으로 가져올 수 있네요

곡 : <br>
![image](https://github.com/Hyeji1364/Hyeji1364/assets/161557112/e4c8d282-b85d-4192-880e-ef414e0a809b)

▶ 곡은 'title > a '로 가져오면 되구요~

아티스트 : <br>
![image](https://github.com/Hyeji1364/Hyeji1364/assets/161557112/6872e16e-4fc7-4e59-92d4-a1bcd1177384)
▶ 'artist > a:nth:child(1)' 이렇게 가져오는 이유는 가수가 피쳐링을 포함해서 2명인 경우도 있기 때문에, 첫번째 요소만 가져오기 위해 이렇게 설정해주는 것입니다.

이제 데이터 요소를 어떻게 선택해 가져와야하는지 알았으니, json파일로 저장해봅시다!

<br>

### bugsmusic 데이터 불러오기

````python
cd python
python bugsMusic.py
````
<br>

````
import requests as req
from bs4 import BeautifulSoup as bs
import pandas as pd

res = req.get("https://music.bugs.co.kr/chart")

soup = bs(res.text, "lxml")

# 데이터 선택
ranking = soup.select(".ranking > strong")
title = soup.select(".title > a")
artist = soup.select(".artist > a:nth-child(1)")

# 데이터 저장
rankingList = [r.text.strip() for r in ranking]
titleList = [t.text.strip() for t in title]
artistList = [a.text.strip() for a in artist]

# 데이터 프레임 생성
chart_df = pd.DataFrame ({
    'Rank': rankingList,
    'Title' : titleList,
    'Artist': artistList
})

# JSON 파일로 저장
chart_df.to_json("bugsChart100.json", force_ascii=False, orient="records")
````
이렇게 되면 

![image](https://github.com/Hyeji1364/Hyeji1364/assets/161557112/339b6ef1-96ae-46f5-94e4-84e7615f90dc)

bugsChart100.json파일이 생성됩니다!
내용을 보면

![image](https://github.com/Hyeji1364/Hyeji1364/assets/161557112/68c90807-a549-4dcf-a21d-ead95751f1ef)

이렇게 차트의 Rank, Title, Artist 순으로 Top100까지 순위가 나옵니다!
여기까지 나오면 성공하셨습니다 ! 👏🏼👏🏼 🙌🏼 

그럼 지금까지 벅스의 Top100 차트를 json파일로 가져오기에 대해 알아보았습니다.