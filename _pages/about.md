---
title: 
layout: single
permalink: /about/
author_profile: true
sidebar_main: ture
classes: wide
---

<style>
  * {margin:0;padding:0;box-sizing:border-box;}
  ul, li {list-style:none;}
  
  [name="slide"] {display:none;}
  .slidebox {max-width:300px;width:100%;margin: 10px; float:right; text-align:center;}
  .slidebox img {max-width:100%;}
  .slidebox .slidelist {
    white-space:nowrap;
    font-size:0;
    overflow:hidden;
  }
  .p1 {margin-right:15; padding-right: 5px}

  .p2 {clear: both}

  .slidebox .slideitem {
    position:relative;
    display:inline-block;
    vertical-align:middle;
    width:100%;
    transition:all .35s;
  }
  .slidebox .slideitem label {
    position:absolute;
    z-index:1;
    top:50%;
    transform:translateY(-50%);
    padding:20px;
    border-radius:50%;
    cursor:pointer;
  }
  label.left {
    left:20px;
    background-color:#eaeaea 20%;
    background-image:url('/assets/images/arrow/left-arrow.png');
    background-position:center center;
    background-size:50%;
    background-repeat:no-repeat;
  }
  label.right {
    right:20px;
    background-color:#eaeaea 20%;
    background-image:url('/assets/images/arrow/right-arrow.png');
    background-position:center center;
    background-size:50%;
    background-repeat:no-repeat;
  }
  
  /* 페이징 스타일 */
  .paginglist {text-align:center;padding:30px 0;}
  .paginglist > li {display:inline-block;vertical-align:middle;margin:0 10px;}
  .paginglist > li > label {display:block;padding:10px 30px;border-radius:10px;background:#ccc;cursor:pointer;}
  .paginglist > li:hover > label {background:#333;}
  
  [id="slide01"]:checked ~ .slidelist .slideitem {transform:translateX(0);animation:slide01 20s infinite;}
  [id="slide02"]:checked ~ .slidelist .slideitem {transform:translateX(-100%);animation:slide02 20s infinite;}
  [id="slide03"]:checked ~ .slidelist .slideitem {transform:translateX(-200%);animation:slide03 20s infinite;}
  [id="slide04"]:checked ~ .slidelist .slideitem {transform:translateX(-300%);animation:slide04 20s infinite;}
  
  @keyframes slide01 {
    0% {left:0%;}
    23% {left:0%;}
    25% {left:-100%;}
    48% {left:-100%;}
    50% {left:-200%;}
    73% {left:-200%;}
    75% {left:-300%;}
    98% {left:-300%;}
    100% {left:0%;}
  }
  @keyframes slide02 {
    0% {left:0%;}
    23% {left:0%;}
    25% {left:-100%;}
    48% {left:-100%;}
    50% {left:-200%;}
    73% {left:-200%;}
    75% {left:100%;}
    98% {left:100%;}
    100% {left:0%;}
  }
  @keyframes slide03 {
    0% {left:0%;}
    23% {left:0%;}
    25% {left:-100%;}
    48% {left:-100%;}
    50% {left:200%;}
    73% {left:200%;}
    75% {left:100%;}
    98% {left:100%;}
    100% {left:0%;}
  }
  @keyframes slide04 {
    0% {left:0%;}
    23% {left:0%;}
    25% {left:300%;}
    48% {left:300%;}
    50% {left:200%;}
    73% {left:200%;}
    75% {left:100%;}
    98% {left:100%;}
    100% {left:0%;}
  }
  </style>
  
  <div class="slidebox">
    <input type="radio" name="slide" id="slide01" checked>
    <input type="radio" name="slide" id="slide02">
    <input type="radio" name="slide" id="slide03">
    <input type="radio" name="slide" id="slide04">
    <ul class="slidelist">
      <li class="slideitem">
        <div>
          <label for="slide04" class="left"></label>
          <label for="slide02" class="right"></label>
          <a><img src="/assets/images/IMG_0706.jpeg"></a>
        </div>
      </li>
      <li class="slideitem">
        <div>
          <label for="slide01" class="left"></label>
          <label for="slide03" class="right"></label>
          <a><img src="/assets/images/IMG_8532.JPG"></a>
        </div>
      </li>
      <li class="slideitem">
        <div>
          <label for="slide02" class="left"></label>
          <label for="slide04" class="right"></label>
          <a><img src="/assets/images/IMG_6526.jpeg"></a>
        </div>
      </li>
      <li class="slideitem">
        <div>
          <label for="slide03" class="left"></label>
          <label for="slide01" class="right"></label>
          <a><img src="/assets/images/IMG_8157.jpeg"></a>
        </div>
      </li>
    </ul>
    <!-- <ul class="paginglist">
      <li>
        <label for="slide01"></label>
      </li>
      <li>
        <label for="slide02"></label>
      </li>
      <li>
        <label for="slide03"></label>
      </li>
      <li>
        <label for="slide04"></label>
      </li>
    </ul> -->
  </div>
  
  <h1>Welcome!</h1>
  <p class="p1">Hello, my name is Eunkyung, but you can call me Ara. My parents chose the name Ara for me when I was born, and when combined with my last name Jo, it forms the pleasant phrase "I like it!" <br><br>
      I majored in social psychology for my bachelor's degree and criminal psychology for master's degree 
      in <a href="https://www.sookmyung.ac.kr/sites/sookmyungen/index.do">Sookmyung Women's University</a>.<br><br>
      I love swimming, learning something new (coding these days), and talking with new people.</p> 
  
  <p class="p2"><h2>Research Interests</h2>
    My research interests are centered around understanding how people make decisions and judgments, particularly in moral situations. 
    I am also intrigued by the impact of social norms on the moral judgment process. 
    For my master's thesis, I conducted research on the topic of victim and perpetrator blaming in various crimes, such as assault, rape, and murder, with the goal of uncovering the fundamental process of blame judgment in criminal cases. <br><br>
  
    
  <h2> Working Experiences</h2> 
    I worked as a research assistant and researcher after my master's studies. 
    I worked at the <a href="https://www.kicj.re.kr/international/">Korean Institute of Criminology and Justice</a>, where I participated in several projects, including data collection from legal cases of sexual crime and the development of textbooks and guidelines to prevent secondary victimization, which are the result of interaction between moral judgment of individuals and social norms. <br></p>
  