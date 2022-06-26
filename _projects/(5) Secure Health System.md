---
name: Secure Health System
tools: [Python, ReactJS, hyperledger, pytorch, mongoDB]
image: /images/shs.png
description: Employing methods of secure web communication techniques along decentralized storage and ML techniques for fraud detection to build a secure healthcare online system.
---

# Secure Healthcare system.
The project aims at building a web application for handling a hospital system and incorporating security-related topics taught in the CSE 579 to make the system robust against any cyber-attacks by securing critical operations and protecting private information.
I led this project which was a huge undertaking with all the verticles (frontend, backend, Ml models, and blockchain setup) done from scratch.

Below are a few important topics that were unique to our project.

### 1. Secure web communication.<br>
Along with employing normal web communication protocols to secure the communication between frontend-backend-DB and blockchain, we also employed an end-point encryption technology which would make deciphering of the payload impossible even if the raw payload is leaked/hijacked.
Below is the sequence diagram to achieve this.
![preview](/images/end_point.png)


### 2. Block-chain Planning<br>
Hyperledger framework was used to securely register all the completed transactions, which can be securely accessed by patients.
Extra security precaution like storing encrypted payload was done so that breach in third-party blockchain provider will not have significant privacy data leakage.
![preview](/images/blockchain.png)

### 3. Malicious login prevention.<br>
We used the NSL-KDD dataset to train a model capable of preventing malicious login attempts, along with this we also included a ReCaptcha and login try count mechanism to aid the model in the prediction of malicious login.
![preview](/images/malicious.png)


<p class="text-center">
{% include elements/button.html link="https://github.com/Pavan-pk/AI_algorithms" text="Project repository" %}
</p>