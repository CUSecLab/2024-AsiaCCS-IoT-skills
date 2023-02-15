# Command Hijacking on Voice-Controlled IoT in Amazon Alexa Platform

## Introduction

In this work, we design and develop the IOTSKILLANALYZER, which is a scalable and robust testing tool to identify skills with problematic interaction model and backend code. We make the following contributions:

* New tool development: We designed and developed the first dynamic testing tool, named IOTSKILLANALYZER, to examine IoT skills in the Alexa skill store. Our tool can automatically enable testing skills and their related devices, analyze input/output utterances, and extract skills’ logs for abnormal detection.

* New intent hijacking attack. We discovered a new vulnerability in the intent matching process, which can hijack Alexa’s built-in voice commands to invoke malicious
skills. This attack is different from existing squatting attacks because attackers do not need to mimic the pronunciation, but using the exactly same command to hijack skill invocations. We found an effective method to exploit the intent matching process to increase the invocation priority of a malicious skills when users issue
a common voice command (e.g., Alexa’s built-in voice command) of a benign skill.

* Findings: Comprehensive security analysis of IoT skills. With IOT-SKILLANALYZER, we were able to test 588 Alexa IoT skills and collected 536 textual log outputs. We identified 67 skills with potential problems. We also conducted a comprehensive user review analysis to further identify potential problematic IoT skills. We found 26 skills have unsolicited behaviors when it comes to controlling IoT devices, such as failing to control device, doing unexpected tasks, or providing wrong device controlling information to users. 


## Major findings
### Here is a demo for the smart home different category skill hijacking. 

[![Watch the video](https://github.com/voice-assistant-research/IoT-skills/blob/main/images/youtube3.png)](https://youtu.be/Q5y1)

### Here is a demo for the smart home customized built-in intent hijacking. 

[![Watch the video](https://github.com/voice-assistant-research/IoT-skills/blob/main/images/youtube2.png)](https://youtu.be/Q5y1w-l0)


### Here is a demo for the connected car skill hijacking with customized intent. 

[![Watch the video](https://github.com/voice-assistant-research/IoT-skills/blob/main/images/youtube.png)](https://youtu.be/Q5y1w-lzRt0)


### Problematic Skills in Smart home skills

We tested all 3122 Amazon skills in the smart home category (as of June. 2022). We identified 67 potential wrong implemented skills on the Amazon Alexa’s skill store.

Skill Hijacking Category | # of Skills | Example | Utterances|
:---: | :---: | :---:| :---:|
Built-in Intent | 16 | SPA  | Turn up the temperature |
Keep Dialogues | 8 |Home Miner |  Stop all devices |
Scenario | 17 | My things | Setup guard |


### Skills with unsolicited behaviors

For the skills backend code, we identify skills with potential problems as follows:


![Unsolicited](https://github.com/voice-assistant-research/IoT-skills/blob/main/images/unsolicited.png)


### User reviews

We also use negative user reviews of skills to confirm our findings. We listed the comparison of user reviews from IoT skills with all other skills.

Skill category | IoT skills | All others|
:---: | :---: | :---:| 
Skill number | 3,122 | 76,533  | 
Skill with reviews | 1,319 | 24,844 |  
Review number | 85,731 | 424,071 |  
Average skill reviews | 65 | 17 | 
average negative review number | 20.8 | 2.8  | 
negative review percentage | 32% | 16% |  
Average skill stars | 2.97 | 3.65 | 
