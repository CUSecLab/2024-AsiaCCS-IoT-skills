# Hey Alexa, Close the Garage Door: Understanding Security Risks of Alexa IoT Skills

## Introduction

In this work, we design and develop the IOTSKILLANALYZER, which is a scalable and robust testing tool to identify skills with problematic interaction model and backend code. We make the following contributions:

* New tool development: We designed and developed the first dynamic testing tool, named IOTSKILLANALYZER, to examine IoT skills in the Alexa skill store. Our tool can automatically enable testing skills and their related devices, analyze input/output utterances, and extract skills’ logs for abnormal detection.

* New intent hijacking attack. We discovered a new vulnerability in the intent matching process, which can hijack Alexa’s built-in voice commands to invoke malicious
skills. This attack is different from existing squatting attacks because attackers do not need to mimic the pronunciation, but using the exactly same command to hijack skill invocations. We found an effective method to exploit the intent matching process to increase the invocation priority of a malicious skills when users issue
a common voice command (e.g., Alexa’s built-in voice command) of a benign skill.

* Findings: We identified 6,079 skills and 175 actions violating at least one policy requirement. 590 skills and 24 actions violate more than one policy. In the Kids category, we identified 244 policy-violating skills. 80% of skills and 68% of actions in the Health category violate at least one policy. 623 skills and 25 actions violate policies related to personal data collection. 


## Major findings

### Here is a demo for the connected car skill testing. 

[![Watch the video](https://github.com/skilldetective/skilldetective/images/car.png)](https://www.youtube.com/watch?v=OrYLUcC7zx4_5)

### The detailed list of the identified policy-violating skills/actions can be found in ./[violation](https://github.com/skilldetective/skilldetective/tree/master/policy_detector)

### Skills in Smart home skills

We tested all 3,617 Amazon skills in the smart home category (as of June. 2022). We identified 282 policy-violating skills in the Kids category of the Amazon Alexa’s skill store.

Policy Violation | # of Skills | Example |
:---: | :---: | :---:| 
Collecting personal data | 34 | So, first, what is your name? | 
Directing users to outside of Alexa | 21 | Please support us by visiting www.oneoffcoder.com. | 
Explicit mature content | 12 | My bestie contains mature content that may not be suitable for all ages. | 
Requesting for positive rating | 177 | If you enjoyed playing kid chef, leaving us a five star review will help us add more content. | 
Toxic content | 4 | If I had a face like yours, I’d teach my ass to talk | 
Violation in audios/images | 4 | Happy holidays santa’s little helper here. Tell me your name to begin. (in audio) | 

![Kids](https://github.com/skilldetective/skilldetective/blob/master/images/kids_with_permission.png)

### Skills with data collection

For the general (non-Kids and non-Health) categories, we identified 480 skills and 61 actions collecting personal data without using permission APIs (they collect user data through the conversation interface). There are also 1,369 skills collecting personal data using permission APIs in the Amazon Alexa platform. Among all these skills with data collection, 623 skills and 25 actions violate at last one policy, such as lacking a privacy policy, having an incomplete or deceptive privacy policy.

Policy Violation | Skills Collect Data Through Permission APIs | Skills Collect Data Without Using Permission APIs | Action |
:---: | :---: | :---:| :---:| 
Collecting data | 1,369 | 480 | 61|
Lacking a privacy policy| 1 | 171 | 0 |
Having an ncomplete privacy policy | 330 | 104 |8|
Having a deceptive privacy policy |38|12|2|
Should ask for permission |-|-|17|

![nopolicy](https://github.com/skilldetective/skilldetective/blob/master/images/permission_no_policy2.png)
![deceptivepolicy](https://github.com/skilldetective/skilldetective/blob/master/images/deceptive_policy.png)


### Policy violations in audio/images

We have detected 8 skills with policy violations hidden in the audio or image files. 4 of the skills in the Kids category. 4 non-kid skills contain data collection, while 2 of them lack a privacy policy and 2 more have incomplete privacy policies. The skill "Shape Game" asks "what is your name" in the audio file output, but does not provide a privacy policy.

![Summary](https://github.com/skilldetective/skilldetective/blob/master/images/media_violation.png)


## Summary of policy violations identified by SKILLDETECTIVE
![Summary](https://github.com/skilldetective/skilldetective/blob/master/images/results.png)
