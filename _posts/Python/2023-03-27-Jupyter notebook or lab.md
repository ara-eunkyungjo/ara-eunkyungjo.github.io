---
layout: single
title: "Jupyter notebook / lab"
categories: Python
toc: true
---

# 1. starting python in MacOS terminal
파이썬 버전에 따라서 'python' or 'python3'을 입력한다.

```
python3
```

그러면 아래와 같이 >가 세개 뜨는데, 이러면 파이썬 문법을 사용할 준비가 된 것이다. 

```
>>>
```
여기서 나가고싶으면 ```ctrl+z```를 입력해 빠져나오면 된다.
<br>
그렇지만 너무 못생기고 불편하다! 그래서 쓰는 것이 주피터노트북 혹은 주피터랩이다.

# 2. Jupyter lab 실행하기
아나콘다를 설치하고 터미널에 ```jupyter-lab```을 쳤는데도 주피터랩이 실행되지 않는 경우, 아나콘다 경로설정에 문제가 있어서 그렇다.
터미널에 아래와 같이 적어준 후 다시 실행해보자.
자기 컴퓨터 계정명은 터미널을 켜면 나오는 라인에 적혀있다.


```
export PATH="Users/(자기 컴퓨터 계정명)/anaconda3/bin":${PATH}"
```

입력하고 엔터를 눌러도 별다른 창이 나오지 않는다. 
하지만 다시 ```jupyter-lab```을 입력하면, 잠시 화면이 멈춘 듯 하다가 주피터랩이 실행된다.
주피터랩이 실행된 후에는 터미널에 키를 입력할 수 없다. (주피터랩이 실행중이라서)
주피터랩은 인터넷브라우저에서 실행되지만, 인터넷 연결이 필요한 것은 아니다. 또한, 브라우저를 종료해도 터미널에서 주피터랩을 종료한 것이 아니면 주피터랩이 종료된 것도 아니다.


실수로 브라우저를 닫은 경우, 터미널에서 아래와 같은 주소를 찾아서 브라우저서 다시 열 수 있다.
```
 To access the server, open this file in a browser:
        file:///Users/사용자이름/Library/Jupyter/runtime/jpserver-65592-open.html
    Or copy and paste one of these URLs:
        http://localhost:8888/lab?token=664518c43421bc66fc6182f6c01819258341ab3f4c332d8f
     or http://127.0.0.1:8888/lab?token=664518c43421bc66fc6182f6c01819258341ab3f4c332d8f
```



