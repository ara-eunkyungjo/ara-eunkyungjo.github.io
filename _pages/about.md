---
title:
layout: single
permalink: /about/
author_profile: true
sidebar_main: true
classes: wide
---

<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  ul, li { list-style: none; }

  .slidebox {
    max-width: 400px;
    padding: 20px;
    width: 100%;
    margin: 10px;
    float: right;
    text-align: center;
  }

  .slidelist {
    position: relative;
    overflow: hidden;
    width: 100%;
  }

  .slides-track {
    display: flex;
    transition: transform 0.35s ease;
    width: 100%;
  }

  .slideitem {
    min-width: 100%;
    width: 100%;
  }

  .slide-inner {
    position: relative;
    width: 100%;
    height: 320px; /* 박스 높이 고정 */
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    background: None;
  }

  .slide-inner img {
    max-width: 100%;
    max-height: 100%;
    width: auto;
    height: auto;
    display: block;
  }

  .nav-btn {
    position: absolute;
    z-index: 2;
    top: 50%;
    transform: translateY(-50%);
    width: 40px;
    height: 40px;
    border: none;
    border-radius: 50%;
    cursor: pointer;
    background-color: rgba(234, 234, 234, 0.85);
    background-position: center center;
    background-size: 50%;
    background-repeat: no-repeat;
  }

  .nav-btn.left {
    left: 10px;
    background-image: url('/assets/images/arrow/left-arrow.png');
  }

  .nav-btn.right {
    right: 10px;
    background-image: url('/assets/images/arrow/right-arrow.png');
  }

  .dots {
    display: flex;
    justify-content: center;
    gap: 8px;
    margin-top: 10px;
  }

  .dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    border: none;
    background: #cfcfcf;
    cursor: pointer;
  }

  .dot.active {
    background: #666;
  }

  .p1 {
    margin-right: 15px;
    padding-right: 5px;
  }

  .p2 {
    clear: both;
  }

  @media (max-width: 768px) {
    .slidebox {
      float: none;
      margin: 10px auto 20px auto;
    }
  }
</style>

<div class="slidebox">
  <div class="slidelist">
    <div class="slides-track" id="slides-track"></div>
    <button class="nav-btn left" id="prev-btn" type="button" aria-label="Previous image"></button>
    <button class="nav-btn right" id="next-btn" type="button" aria-label="Next image"></button>
  </div>
  <div class="dots" id="dots"></div>
</div>

<h1>Welcome!</h1>
<p class="p1">
  Hello! My name is Eunkyung (은경 恩卿), and I go by Ara (pronounced "ah-rah"). "Ara" is the name my parents originally chose for me at birth, and when combined with my last name, Jo, it forms a pleasant phrase in Korean meaning "It's good!" or "I like it!" <br><br>

  I am currently working as a lab manager in the <a href="https://sites.lsa.umich.edu/misl/" target="_blank">Mind in Society Lab</a> at the University of Michigan, assisting <a href="https://sites.google.com/umich.edu/npcamp/" target="_blank">Dr. Nick Camp</a>. I majored in social psychology for my bachelor's degree and earned a master's degree in criminal psychology from <a href="https://www.sookmyung.ac.kr/sites/sookmyungen/index.do" target="_blank">Sookmyung Women's University</a>.<br><br>

  I love trying and learning new things! Over the past few years since moving to the U.S., I’ve tried several things, including skateboarding, crochet, and sewing... and these days, I’m building the ultimate cat toy using electronic parts from Amazon!
</p>

<div class="p2">
  <h2>Research Interests</h2>
  <p>
    My research interests are centered on understanding how people make decisions and judgments, particularly in moral situations.
    I am also intrigued by the impact of social norms on the moral judgment process.
    For my master's thesis, I conducted research on the topic of victim and perpetrator blaming in various crimes, such as assault, rape, and murder, with the goal of uncovering the fundamental process of blame judgment in criminal cases.
  </p>
  

  <!-- <h2>Working Experiences</h2>
  <p>
    I worked as a researcher for few years after my master's studies.
    I worked at the <a href="https://www.kicj.re.kr/international/" target="_blank">Korean Institute of Criminology and Justice</a>, where I participated in several projects, including data collection from legal cases of sexual crime and the development of textbooks and guidelines to prevent secondary victimization, which are the consequence of interaction between moral judgment of individuals and social norms.
  </p> -->
</div>

<script>
  const images = [
    "/assets/images/2026HWF-Team 7-WEB-2.jpg",
    "/assets/images/jspsychHackathon2025.jpg",
    // "/assets/images/IMG_8532.JPG",
    // "/assets/images/IMG_6526.jpeg",
    // "/assets/images/IMG_8157.jpeg",
  ];

  const slidesTrack = document.getElementById("slides-track");
  const dotsContainer = document.getElementById("dots");
  const prevBtn = document.getElementById("prev-btn");
  const nextBtn = document.getElementById("next-btn");

  let currentIndex = 0;

  function renderSlider() {
    slidesTrack.innerHTML = "";
    dotsContainer.innerHTML = "";

    images.forEach((src, index) => {
      const slide = document.createElement("div");
      slide.className = "slideitem";
      slide.innerHTML = `
        <div class="slide-inner">
          <img src="${src}" alt="Slide ${index + 1}">
        </div>
      `;
      slidesTrack.appendChild(slide);

      const dot = document.createElement("button");
      dot.className = "dot";
      dot.type = "button";
      dot.setAttribute("aria-label", `Go to slide ${index + 1}`);
      dot.addEventListener("click", () => {
        currentIndex = index;
        updateSlider();
      });
      dotsContainer.appendChild(dot);
    });

    updateSlider();
  }

  function updateSlider() {
    slidesTrack.style.transform = `translateX(-${currentIndex * 100}%)`;

    const dots = dotsContainer.querySelectorAll(".dot");
    dots.forEach((dot, index) => {
      dot.classList.toggle("active", index === currentIndex);
    });
  }

  function goPrev() {
    currentIndex = (currentIndex - 1 + images.length) % images.length;
    updateSlider();
  }

  function goNext() {
    currentIndex = (currentIndex + 1) % images.length;
    updateSlider();
  }

  prevBtn.addEventListener("click", goPrev);
  nextBtn.addEventListener("click", goNext);

  renderSlider();
</script>