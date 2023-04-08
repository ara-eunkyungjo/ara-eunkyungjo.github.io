---
layout: single
title: "Basic Vignette Experiment Setting / 기본 비네트 실험 설정"
categories: [PsychoPy]
toc: true
---
<br>

[>>Go to the Repository<<](https://github.com/ara-eunkyungjo/psychopy_BasicExpSetting)

## How to Start
1. Download files in the same folder.<br>
2. If you want to work on the builder, run Psychopy and open 'intro-consent-text-slider.psyexp.'<br>
3. You can also work on '---.py' file if you are familiar to python code.<br>
<br><br>

## Procedure at a Glance

<img src="/assets/images/psychopy/procedure.png" width="900"><br><br>

- 'intro' routine
<img src="/assets/images/psychopy/1.png" width="700"><br><br>

- 'consent' routine
<img src="/assets/images/psychopy/2.png" width="700"><br><br>

- 'stimuli' routine
<img src="/assets/images/psychopy/3.png" width="700"><br><br>

- 'stimuli' routine (w/response)
<img src="/assets/images/psychopy/4.png" width="700"><br><br>

- 'bye' routine
<img src="/assets/images/psychopy/5.png" width="700"><br><br>
<br><br>

## Notes

#### Branch<br>
With loop function, different routines will be presented depending on the participants' answer to the previous routine.<br>
Please check the 'Code' element in each routines.<br>

#### Condition<br>
(1) With xlsx file, you can present the stimulus in randomized order. The xlsx file should be uploaded in the 'stimuliloop' window (Conditions section).<br>
(2) Stimulus are presented in random order (loopType = 'random').<br>

#### Jump to the Last Routine<br>
For participants who do not cosent to the form, codes were added to skip 'consent' and/or 'stimuli' routine and directly go to the last ('bye') routine.<br>
