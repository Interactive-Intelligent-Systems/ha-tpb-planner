# ha-tpb-planner

Human-aware epistemic planning for promoting behavior-change.

### Abstract

This paper introduces an approach to human-aware epistemic planning in which a rational intelligent agent plans its actions for encouraging a human to proceed in a social virtual reality (VR) environment. In order to persuade the human user to execute specific actions, the agent adapts the virtual environment by adjusting motivators in the environment. The agent's model of the human is based on the theory of planned behavior (TPB), a cognitive theory to explain and predict human behavior. The intelligent agent manipulates the environment, a process where the agent conducts epistemic actions, i.e., adapting the environment and observing human responses, in order to understand the human's behavior and encourage human actions. An action reasoning framework is introduced that defines transitions between goal-oriented human activities in the virtual scenario. The proposed human-aware planning architecture can also be applied in environments that are not virtual, by utilizing modern mobile devices which have built-in sensors that measure motion, orientation, and various environmental conditions. 

### Prerequisites

DLV system: http://www.dlvsystem.com/dlv/#1

DLV is an artificial intelligence system based on disjunctive logic programming.

### Running the planner

Command line: DLV hap.plan hap.dl -FP -N=4

Example output:

-- DLV [build BEN/Dec 17 2012   gcc 4.6.1]

-- STATE 0: at(human,lobby), attitude_stress(3), control_stress(3), guides(1), light(3), normative_stress(3), sound(3)
-- ACTIONS: increase_guides(2)
-- STATE 1: light(3), normative_stress(3), sound(3), attitude_stress(3), at(human,lobby), -guides(1), -control_stress(3), guides(2), control_stress(2)
-- ACTIONS: decrease_sound(2)
-- STATE 2: light(3), normative_stress(3), -sound(3), -attitude_stress(3), sound(2), attitude_stress(2), at(human,lobby), guides(2), control_stress(2)
-- ACTIONS: decrease_light(2)
-- STATE 3: -light(3), -normative_stress(3), light(2), normative_stress(2), sound(2), attitude_stress(2), at(human,lobby), guides(2), control_stress(2)
-- ACTIONS: move(queue)
-- STATE 4: light(2), normative_stress(2), sound(2), attitude_stress(2), -at(human,lobby), control_stress(3), at(human,queue), guides(2), control_stress(2)

-- PLAN: increase_guides(2); decrease_sound(2); decrease_light(2); move(queue)

The aim of the human-aware planner agent is to adapt the environment in order to change the mental state of the human. The planner agent is modeled as an action theory (D,O), utilizing a domain description D, which explains how human mental states relate to fluents of the environment, and a set of observations O, i.e., the observable environment, such as lights, sounds, and people, and the partly observable mental state of the human, i.e., attitude stress, normative stress, and control stress.

The agent models a human agent, utilizing the observed human actions in the environment and causal laws, specified for the planner agent's adaptive actions of the environment, to estimate the human's future actions. The planner agent's generated plan can be represented as a trajectory; a sequence of actions leading from a starting configuration of fluents towards a goal configuration of fluents. Each action directly changes fluents of the environment and indirectly changes fluents of the mental state of the human. Run the planner for a demonstration of the planner agent's planning process in response to a set of observations in the cafeteria scenario. Initially, the code will plan a transition from the lobby area to the queue area.

### Authors

Andreas Brännström {andreasb@cs.umu.se}
Timotheus Kampik {tkampik@cs.umu.se}
Juan Carlos Nieves {jcnieves@cs.umu.se}

Department of Computing Science
Umeå university
SE-901 87, Umeå, Sweden
