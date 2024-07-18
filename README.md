# AUTONOMOUS LINE FOLLOWING gym (ALF-g)

## Goal

In many countries, teenagers have to wait until the age of around 18 before they are granted the autonomy to sit behind the wheel of a car and follow lanes (i.e., lines) around the road networks of the world. Driving certainly has many complexities aside from the lane-following, and lane-following can be more or less complex depending on the situation, for example:

* Driving on a straight 3-lane highway; **versus**
* Driving down a steep and windy mountain road in heavy rain/sleet.

By contrast, many primary school students are entrusted with programming an autonomous algorithm for a "lego robot" (or similar) to follow a high-contrast line using a downwards-facing infra-red (IR) sensor. Certainly, there are vastly lower consequences if the "lego robot" goes rogue.

All that said, the goal of this Autonomous Line Following gym (or ALF-g for short) is to find a middle ground between the previous two examples:

---
> **OUR GOAL** is to build up from scratch a gymnasium-like environment (i.e., a simulation environment) for autonomous driving of a car to follow a continuous line when using line-detection feedback via a forward-facing camera and operating in dynamically challenging conditions.
---

## Outline

In order to achieve this goal, we build up the environment over the following major sections:

* **First:** we select and define the kinematic bicycle model, which is what we use for modeling a car.
* **Second:** we build a class for simulating a kinematic bicycle model, and we do so in a fashion that is devoid of any meaningful operating environment.
* **Third:** we build a class for a road environment (i.e., a line), and we do so in a fashion that is devoid of any robots to drive along the road.
* **Fourth:** we build a gymnasium-like class for road-following simulation (i.e., line-following), and we do this by utilizing the bicycle model and road environment from the previous two sections.

**NOTE:** For the purpose of getting simulating quickly, **you can safely jump** straight to the fourth major section, and then refer back to the other sections if there are details that you wish to check or change.

## Dependencies

We develop ALF-g fully in Python and we purposefully choose to avoid "exotic" modules to emphasize the from-scratch nature, as well as to make ALF-g easier to run on any computer. The dependencies are: `numpy`, `scipy`, `matplotlib`.

## Reinforcement Learning Approaches

In our simulation environment, we employ two advanced reinforcement learning algorithms to train the autonomous driving agent:

* **Soft Actor-Critic (SAC):** An off-policy actor-critic algorithm that aims to maximize both the expected reward and the entropy of the policy, leading to more stable and efficient learning.
* **Proximal Policy Optimization (PPO):** An on-policy optimization algorithm that uses a surrogate objective function to improve the stability and reliability of the policy updates.
