# Reading Notes

## general questions

1. what is a 'model' in model-based testing?
2. what is systematic testing

## general Notes

### Fuzz Testing

cons:

* redundent inputs
* not suitable for inputs requiring human intelligence.
* can't generate pecific inputs that control the app's functionality
* **Monkey** only generate UI events, not system events

### tools

GUITAR framework.

## Reinforcement Learning Based Curiosity-driven Testing of Android Applications

### Citation

Minxue Pan, An Huang, Guoxin Wang, Tian Zhang, and Xuandong Li. **Reinforcement Learning Based Curiosity-driven Testing of Android Applications**. In *Proceedings of the 29th ACM SIGSOFT International Symposium on Software Testing and Analysis*, pp. 153-164. July 18–22, 2020, Virtual Event, USA.

### 问题

1. activity, scenario? state？

   An **Android activity** is one screen of the Android app's user interface. In that way an Android activity is very similar to windows in a desktop application. An Android app may contain one or more activities, meaning one or more screens.

   **Fragment** represents a behavior **or** a portion of user interface in an **Activity**. You can combine multiple **fragments** in a single **activity** to build a multi-pane UI and reuse a **fragment** in multiple activities

2. state 动态增加，对于 Q-learning 是否有影响？

### 主要特点

1. 基于神经网络的场景分割（scenario division），更加有效得来判断是否是不同的状态
2. 通过强化学习 Q-learning，来驱动到更加不同的 state。将测试过程建模为 MDP。

## Dynodroid: An input generation system for android apps. 

### citation

Aravind Machiry, Rohan Tahiliani, and Mayur Naik. 2013. **Dynodroid: An input generation system for android apps. In Proceedings of the 2013 9th Joint Meeting on Foundations of Software Engineering.** ACM, 224–234

### Notes

Dynodroid views an app as an event-driven program that interacts with its environment by means of a sequence of events through the Android framework. 

Use reaction of the app upon each event to guide next event.

It uses a novel “observe-select-execute” principle to efficiently generate a sequence of inputs to an app. 

#### Fuzz Testing

##### features

* generate large number of random UI events

* balck-box approach

##### pros

* easy to implement
* fully automatic
* large number of events

##### cons

* redundent inputs
* not suitable for inputs requiring human intelligence.
* can't generate pecific inputs that control the app's functionality
* **Monkey** only generate UI events, not system events

#### Systematic Testing

apply symbolic execution to generate inputs.

Symbolic execution **automatically partitions the domain of inputs** such that each partition corresponds to a unique program behavior (e.g., execution of a unique program path).

##### features

* white box

##### pros

* less redundant inputs

##### cons

* requires heavily instrumenting the app
* difficult to scale due to the notorious path explosion problem

#### model-based

##### features

model-based testing requires users to **provide a model of the app’s GUI** [24, 27], though automated GUI model inference tools tailored to specific GUI frameworks exist as well [8, 23].

Model-based testing harnesses human and framework knowledge to abstract the input space of a program’s GUI, and thus reduce redundancy and improve efficiency

##### pros

##### cons