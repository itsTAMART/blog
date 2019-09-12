---
layout: post
title: Reinforcement Learning for Navigation 
date: 2019-09-11 00:00:00 +0300
description: Experimenting with Reinforcement Learning and going beyond Cartpole, I created an environment with AirSim
img: airsim-env.gif # Add image post (optional)
tags: [Reinforcement Learning, Navigation] # add tag

---

Experimenting with **Reinforcement Learning** (and going beyond Cartpole) I created an environment with AirSim to **learn how to navigate**. In the process I also created a faster 2D environment with similar dynamics that included **Curriculum Learning** features to speed up training. I trained several agents with the [Stable Baselines Library](https://github.com/hill-a/stable-baselines) and **transferred one policy into the AirSim environment**. The results of the transferred policy can be seen in the video below.

# Reinforcement Learning for Navigation





<iframe width="560" height="315" src="https://www.youtube.com/embed/CfLkdpxGZgA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>





The process started hooking up the [AirSim API](https://microsoft.github.io/AirSim/) to the [OpenAI gym](https://github.com/openai/gym) interface and training on simple tasks like reaching the target without any obstacles. Then as training agents was taking so long, I created a **2D environment** mainly using **NumPy and Shapely** that supported many different configurations. The new environment meant a **x100 increase in training speed**, so we could approach more complex tasks. A visualization of the agent learning in the 2D environment can be seen in the GIF below. 



![learned_bot_behaviours.gif]({{site.baseurl}}/assets/img/learned_bot_behaviours.gif)



The environment was designed to work independently of the map size and the obstacle positions, and it supported a **Curriculum Learning** mode that increased difficulty as the agent progressed. It also supported Sparse and Dense Rewards and Discrete and Continuous actions. Finally after training different seeds for 60M timesteps in a complex setup, I took the best performing policy and deployed it on an agent in the **AirSim environment**. The agent was able to retain some performance even tho the dynamics were different and some of the successful trajectories are shown in the video at the top. *For more information on the whole experiment head to the Master Thesis links at the bottom of the post.* 



The development of this experiment led to a **paper** published in the  *27th European Signal Processing Conference, EUSIPCO 2019* and to the writing of my **Master Thesis** for the *Master of Signal Processing and Machine Learning in Universidad Politécnica de Madrid*. The links to both documents are below as well as the link for the **code** of the environment.



![paper_unrolled.png]({{site.baseurl}}/assets/img/paper_unrolled.png)





*link to Master Thesis: [link](https://github.com/itsTAMART/Master-Thesis/blob/master/MasterThesis_Daniel_Tapia.pdf)*

*link to Paper: [link](https://github.com/itsTAMART/Master-Thesis/blob/master/Tapia2019Deep.pdf)*

*link to Code: [link](https://github.com/itsTAMART/UAV-RL-environment)*
