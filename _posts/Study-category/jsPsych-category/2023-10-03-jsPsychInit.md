---
layout: single
title: "jsPsych 실험 설계 구조: timeline과 trial"
categories: [jsPsych]
toc: true
---

<br>

## 1. timeline과 trial의 관계
timeline은 이름처럼 실험의 흐름을 짚어주는 기능을 한다.
timeline은 통상 array로 구성하며, 그 안에 각 trial이 들어가게 된다.
array는 말그대로 '접시/그릇'인데, 여러 요소를 담고 있는 집합으로 생각하면 되는 것 같다. 

timeline = (trial 1) -> (trial 2) -> (trial 3) -> ... (last trial) <br><br>
timeline 안의 각 trial을 실행하기 위해서는 `timeline.push(trial_name)`을 입력하는데, 이렇게 하면 `'trial_name'`에 해당하는 trial이 실행된다.
여러 trial을 진행하고자 한다면, 
```html
timeline.push(trial1); 
timeline.push(trial2); ...
``` 
식으로, 진행하고자 하는 trial을 순서대로 푸시해주면 된다.
<br>
<br>

## 2. trial 설정하기
### 2-1. trial이란?
trial은 '시행' 이라는 뜻으로, 실험에서 자극을 제시하고 응답을 받는 과정을 하나로 묶어 trial로 표현한다.
예를 들어, 사진을 보여주고 해당 사진에 대한 긍정-부정 평가를 5점 리커트 척도로 하고자 한다면, 화면에 사진을 제시하고 참가자들이 응답을 제출하는 과정이 한 trial이 된다. <br>
다른 예로 stroop 과제를 들자면, <색깔이 입혀진 단어 *하나*를 보고 무슨 색인지 응답하는 것>이 trial이 되고, trial이 모여서 과제가 된다고 볼 수 있다. 
심리학 실험에서 trial이 소수만 있는 경우는 매우 드물 것이고, 비슷한 과제를 반복해서 시행하는 경우가 많을 것이므로 trial의 이름을 정할 때 헷갈리지 않도록 잘 정해주는 것이 좋다. <br>

### 2-2. trial 셋팅하기
각 trial은 변수다. 따라서 `var`를 이용해서 변수를 선언해줘야 한다.

```js
var trial_name = {
    type: jsPsychHtmlKeyboardResponse,
    stimulus: 'This is trial 1.' 
}
```

- trial에게 이름주기: 위의 예시에서 `trial_name`에는 해당 시행의 이름이 들어가게 된다. 예를 들어, 두 개의 사진을 보여주고 차이점을 찾아내는 실험을 한다고 가정하면, 해당 trial은 'changeDetection' 정도가 되겠다.<br>

- trial의 속성 정하기: 그 아래의 `type`과 `stimulus`는 해당 시행의 속성을 설정해주는 부분이다. 특히 여기서 `type`에 들어가는 이름은 jsPsych에서 제공하는 플러그인, 혹은 누군가가 (어쩌면 스스로가) 만든 플러그인을 입력해준다. 위의 예시에 나오는 `jsPsychHtmlKeyboardResponse`는 html 형식으로 자극을 제공하고, 참가자들이 키보드로 응답을 하면 해당 응답을 수집해주는 플러그인이다.<br>
심리학 실험의 시행이 기본적으로는 '자극제시-응답'이기 때문에 'stimulus'와 'response'는 여러 플러그인이 parameter로 가지고 있다. 하지만 가끔 비슷한 기능을 하는 플러그인에서 비슷한 기능을 하는 parameter의 이름이 약간씩만 다른 경우가 있기때문에 항상 내가 사용하고 있는 플러그인의 paramater가 어떻게 설정되어있는지 확인해주는 것이 좋다. 

<br>
<br>
## 2. timeline
timeline array를 만들기 위해 아래와 같이 `timeline` 변수를 설정해준다.

```html
 <!DOCTYPE html>   
<html>
.
.
.
  <script>
    const jsPsych = initJsPsych(); 

    var timeline = []; // "timeline이라는 변수는 array로, 여러 시행으로 구성될 것입니다."
  </script>
</html>
```

이렇게 설정하면 타임라인의 이름 자체가 timeline으로 설정된 것이다. 한 실험에서 여러 타임라인을 설정하고 싶다면, 해당 타임라인을 시작하기 전에 위와 같이 `var timeline_name =[];`를 입력해서 '앞으로 `timeline_name`이라는 이름의 타임라인을 구성하기 시작할 것입니다' 하고 알려주면 된다.

### (응용) 조건에 맞는 자극 생성하기
timeline 기능을 잘 이용하면 아래와 같이 조건에 맞는 자극을 생성하는 코드를 짤 수도 있다. 
```js
var stimuli = []
    for (`condition 설정에 관한 for문 입력`){
            var stimuli_for_condition = []
                for ('for문 입력'){
                    if ('if문 입력'){
                        `if문 입력 계속`;
                    }
            }
        }
        stimuli.push(stimuli_for_condition);
```
여기서 타임라인은 `stimuli`라는 이름을 가지게 되고, 기존의 `timeline.push(trial_name)`에 타임라인과 trial의 이름을 각각 넣어주면 된다. 

<br>
<br>

## 3. 실험 실행하기
jsPsych 셋팅, 타임라인 및 시행을 모두 설정했다면 실험을 실행시킬 수 있다.

```html
 <!DOCTYPE html>   
<html>
.
.
.
  <script>
    const jsPsych = initJsPsych(); 

    var timeline = []; // "timeline이라는 변수는 array로, 여러 시행으로 구성될 것입니다."
    
    var example_trial = {  // "여기부터 실험의 시행 하나를 설정하겠습니다."
        type: jsPsychSurveyLikert,  //"이 시행은 SurveyLikert라는 jsPsych플러그인을 사용할 것이구요"
        questions: [ //"문항은 이렇게 됩니다."
            {
                prompt: '나는 jsPsych가 심리학 실험을 구성하는 데 유용하다고 생각한다' //"질문"
                labels: [ //"리커트 선택지 라벨"
                    "아주 동의하지 않는다", 
                    "동의하지 않는 편이다", 
                    "보통이다", 
                    "동의하는 편이다", 
                    "매우 동의한다"
                ]
            }
        ],
    },

    timeline.push(example_trial) //"'example trial'을 'timeline'에 포함시켜주세요"

    jsPsych.run(timeline) //'timeline'이라는 이름의 타임라인 실행
  </script>
</html>
```