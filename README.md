# Hey Alexa, Close the Garage Door: Understanding Security Risks of Alexa IoT Skills

## Introduction

In this work, we design and develop the IOTSKILLANALYZER, which is a scalable and robust testing tool to identify skills with problematic interaction model and backend code. We make the following contributions:

* New tool development: We designed and developed the first dynamic testing tool, named IOTSKILLANALYZER, to examine IoT skills in the Alexa skill store. Our tool can automatically enable testing skills and their related devices, analyze input/output utterances, and extract skills’ logs for abnormal detection.

* New intent hijacking attack. We discovered a new vulnerability in the intent matching process, which can hijack Alexa’s built-in voice commands to invoke malicious
skills. This attack is different from existing squatting attacks because attackers do not need to mimic the pronunciation, but using the exactly same command to hijack skill invocations. We found an effective method to exploit the intent matching process to increase the invocation priority of a malicious skills when users issue
a common voice command (e.g., Alexa’s built-in voice command) of a benign skill.

* Findings: Comprehensive security analysis of IoT skills. With IOT-SKILLANALYZER, we were able to test 588 Alexa IoT skills and collected 536 textual log outputs. We identified 67 skills with potential problems. We also conducted a comprehensive user review analysis to further identify potential problematic IoT skills. We found 26 skills have unsolicited behaviors when it comes to controlling IoT devices, such as failing to control device, doing unexpected tasks, or providing wrong device controlling information to users. 


## Major findings

### Here is a demo for the connected car skill testing. 

[![Watch the video](https://github.com/voice-assistant-research/IoT-skills/blob/main/images/combine1.png)](https://youtu.be/3No2eCBTq-s)

### The detailed list of the hijackable utterances can be found in here:

![Summary](https://github.com/voice-assistant-research/IoT-skills/tree/main/images/car_summary.png)

### Skills in Smart home skills

We tested all 2,332 Amazon skills in the smart home category (as of June. 2022). We identified 67 potential wrong implemented skills on the Amazon Alexa’s skill store.

Skill Hijacking Category | # of Skills | Example |
:---: | :---: | :---:| 
Built-in Intent | 16 | SPA  | 
Keep Dialogues | 8 |Home Miner | 
Scenario | 17 | My things | 


![Summary](https://github.com/voice-assistant-research/IoT-skills/tree/main/images/hijacking.png)

### Skills with unsolicited behaviors

For the skills backend code, we identify 

Skills |  |  |
:---: | :---: | :---:| :---:| 
Skills with extra behaviors | 1,369 | 480 | 61|
Skills with wrong behaviors| 1 | 171 | 0 |
Having an ncomplete privacy policy | 330 | 104 |8|
Having a deceptive privacy policy |38|12|2|
Should ask for permission |-|-|17|

![Unsolicited](https://github.com/voice-assistant-research/IoT-skills/tree/main/images/deceptive_policy.png)


### User reviews

We have detected 8 skills with policy violations hidden in the audio or image files. 4 of the skills in the Kids category. 4 non-kid skills contain data collection, while 2 of them lack a privacy policy and 2 more have incomplete privacy policies. The skill "Shape Game" asks "what is your name" in the audio file output, but does not provide a privacy policy.

![Summary](https://github.com/voice-assistant-research/IoT-skills/tree/main/images/user_review.png)


## Summary of our findings
![Summary](https://github.com/voice-assistant-research/IoT-skills/tree/main/images/results.png)
