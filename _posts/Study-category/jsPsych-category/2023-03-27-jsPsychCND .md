---
layout: single
title: "jsPsych 시작하기"
categories: [jsPsych]
toc: true
---

CND는 Content Delivery Network의 약자로, 많은 양의 정보를 네트워크에 보관하고 그때 그때 꺼내오는 방식을 말한다. <br>
이 방식은 가장 간단한 방법으로, jsPsych를 사용하기 위해 필요한 파일들을 CDN에서 다운받아서 사용하는 방식이다.<br>
별도로 jsPsych 파일을 다운받을 필요 없이 CDN에서 필요한 항목을 불러올 수 있다. <br>
CND방식을 활용해 jsPsych를 시작해보자. <br>

## (1) HTML 파일 만들기
 실험 파일을 만들 폴더를 설정하고 실험을 구현할 HTML 파일을 만든 후, HTML기본 틀을 만들어준다. <br>
 주로 Visual Studio Code를 활용한다.
```html
<!DOCTYPE html>    <!--문서의 종류가 html이라고 알려주기-->
<html>
  <head>
    <title>My experiment</title>  <!--실험 제목-->
  </head>
  <body></body>
</html>
```
<br>

## (2) 라이브러리 불러오기
 ```head```태그 안에 jsPsych 라이브러리를 사용하겠다고 알려준다.
```html
 <!DOCTYPE html>   
<html>
  <head>
    <title>My experiment</title> 
    <script src="https://unpkg.com/jspsych@7.3.2"></script>  <!--jsPsych 사용하겠습니다~-->
  </head>
  <body></body>
</html>
```
<br>

## (3) 스타일 시트 불러오기
jsPsych는 실험을 구성하기 위한 스타일 시트도 제공한다. <br>
이걸 사용하겠다고 입력하자.  
```html
 <!DOCTYPE html>   
<html>
  <head>
    <title>My experiment</title> 
    <script src="https://unpkg.com/jspsych@7.3.2"></script> 
    <link href="https://unpkg.com/jspsych@7.3.2/css/jspsych.css" rel="stylesheet" type="text/css" />  <!--jsPsych 스타일 시트 사용하겠습니다~-->
  </head>
  <body></body>
</html>
```
<br>

## (4)실험 구성 공간 만들기
실험 내용은 ```script```태그 안에 작성한다. <br>
```body```태그 아래에 ```script``` 태그를 만들어준다. 

```html
 <!DOCTYPE html>   
<html>
  <head>
    <title>My experiment</title> 
    <script src="https://unpkg.com/jspsych@7.3.2"></script> 
    <link href="https://unpkg.com/jspsych@7.3.2/css/jspsych.css" rel="stylesheet" type="text/css" /> 
  </head>
  <body></body>
  <script>
    //앞으로 실험 구성이 들어갈 자리//
  </script>
</html>
```

<br>

## (5)jsPsych 셋팅 및 초기화
이제 jsPsych를 initialize하자.<br>
관련된 한국어 설명이 거의 없는데, 이 부분은 jsPsych를 사용하기 위한 기본 세팅이라고 생각하면 된다.
```html
 <!DOCTYPE html>   
<html>
  <head>
    <title>My experiment</title> 
    <script src="https://unpkg.com/jspsych@7.3.2"></script> 
    <link href="https://unpkg.com/jspsych@7.3.2/css/jspsych.css" rel="stylesheet" type="text/css" /> 
  </head>
  <body></body>
  <script>
    const jsPsych = initJsPsych(); //jsPsych 기본 세팅//
  </script>
</html>
```
<br>

## (6) 플러그인 추가하기
플러그인은 각 실험의 설정에 맞게 추가해주면 된다. <br>
유의할 점은, ```script``` 태그 안에 플러그인을 추가하고나서 ```head``` 태그 안에 해당 기능을 실행하겠다는 코드를 추가해줘야 한다는 것이다.

