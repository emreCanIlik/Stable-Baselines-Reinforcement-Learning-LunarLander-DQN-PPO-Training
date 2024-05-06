

### Lunar Lander Environment

![Lunar Lander](../../../_images/lunar_lander.gif)

The Lunar Lander environment is part of the Box2D environments in Gym. This environment simulates a classic rocket trajectory optimization problem, where the goal is to land a spacecraft safely on the moon's surface.

#### Action Space
- Discrete(4)

#### Observation Space
- Shape: (8,)
- High: [1.5, 1.5, 5., 5., 3.14, 5., 1., 1.]
- Low: [-1.5, -1.5, -5., -5., -3.14, -5., 0., 0.]

#### Description
This environment offers both discrete and continuous versions. The landing pad is always located at coordinates (0,0). The spacecraft has infinite fuel, allowing agents to learn to fly and land successfully.

#### Actions
There are four discrete actions available:
1. Do nothing
2. Fire left orientation engine
3. Fire main engine
4. Fire right orientation engine

#### Observations
The state is represented by an 8-dimensional vector, including the lander's coordinates, linear velocities, angle, angular velocity, and leg contact status.

#### Rewards
- Landing successfully: 100-140 points
- Moving away from landing pad: Negative reward
- Crashing: Additional -100 points
- Coming to rest: Additional +100 points
- Each leg with ground contact: +10 points
- Engine firing: Negative points per frame

#### Starting State
The lander begins at the top center of the viewport with a random initial force applied to its center of mass.

#### Episode Termination
- Crashing
- Moving outside the viewport
- Lander not awake (body doesn't move or collide)

###  Stable Baselines Integration

![image](https://github.com/emreCanIlik/Stable-Baselines-Reinforcement-Learning-LunarLander-DQN-PPO-Training/assets/118285895/60fbbd06-6f9b-41d5-9bc0-616ade622fd0)

This repository utilizes Stable Baselines, a set of reliable implementations of reinforcement learning algorithms. Both DQN and PPO agents are used to train agents in the Lunar Lander environment.



#### Continuous Environment
To use the continuous environment, specify `continuous=True`. Additional arguments can control gravity, wind effects, and turbulence.

#### Version History
- **v2:** Added energy spent tracking and turbulence effects
- **v1:** Added legs contact with the ground in the state vector
- **v0:** Initial version

#### Credits
Created by Oleg Klimov.

This repository utilizes Stable Baselines, DQN, and PPO agents for reinforcement learning.
