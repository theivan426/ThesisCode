# ThesisCode
Code for optimal execution



## TODO:

Thursday:
- Simulator rebuild
	- Move over to Wandb
		- track action values [DONE]
		- track eval rewards [DONE]
		- track distributions [TODO]
	- Automatic test classification & model saving [PARTIALLY DONE]
- distAgent Cleanup
	- tidy up parameters [DONE]
	- tranisiton to wandb [DONE]
- Continue testing UCB models [DONE]
- Test and work on neural net - look at batch regulisation

Friday:
- Dynamic V_min / V_max depending on vol? [REPLACED WITH IQN]
- distAgent efficiency drive - currently slow to train [POSTPONED]
- Optimise V_max and V_min [DONE]
- Look at reducing plummeting behaviour [DONE?]
- Once optimised, start working on non TWAP optimal environments [POSTPONED]

Monday:
- Testing of new cleaned up code [DONE]
- Get IQN Agent working [STARTED]
- Efficiency possibilities: there are a finite (and not huge) number of states considering only the agents personal environment so some precomputation could be done? [POSTPONED]
- Look at simulations with signal (HFT course notes) [DONE]

Tuesday:
- IQN Agent
	- Get it working
	- Clean up
- Continue cleanup of learningAgent
	- getter / setters, strip out update_params, make more efficient, doccument
- Unit testing?
- Get Crypto Data [DELAYED]

Wednesday
- Test with real data
- Code cleanup
	- QR Agent needs work
	- General cleanup
	- Unittesting?

Thursday & Friday
- Writeup
- Fixes for working with real data

Saturday
- Start work on Stock processing network
- Start cleanup of distAgent, C51 and QR Agent

Thursday 11th
- Trial different terminal periods
- Get running smoothly for real data

Saturday
- Start testing second scale micro intervals with TWAP macro strategy
	- Check k is right
	- decide how we operate (by the second or tick or n seconds?)
		- requires extra layer on real_stock to process
		- talk to Paul about it
	- make sure that period doesnt cross EOD or EOW etc.

Saturday 20th:
- Trading can take place over multiple days currently
- Once I've spoken to Paul need a proper data management system
	- Offload data processing to a seperate class
	- Introduce additional metrics like tick freqeuncy
	- Customisable trading frequency
	- No trading between sessions
	- Possible add correlated currency pairs ?
	- More robust testing system
	- Multiple months?
- Clear up wandb and start adding baselines / choose new standard for evaluation
- Proper statistical evaluation of agents 
- Action values adapt to number of trades [DONE]
- Increase the size of market data

Saturday 4th:
- Limit total LOs to position
- cancel all limit orders when position executed

Monday 6th:
- For now we "remember" the action the agent chooses but not the actual action taken...
	- THIS SHOULD BE CHANGED

Wednesday 8th:
- Need to check how the env responds to changing prices
- Adjust offset between trades and LOB data!

### General Todo
- Sweep over action space
- 

### Agents
- The build model function should probably be broken out of the learning agents
- Fix slightly hacky solution to non generalised parameters
- Test target network concept [DONE]
- Add Sutton and Barto n step approach
- Prioritised Sampling
- Distributional Agent [DONE]


### Simulator
- Silent training option
- Major rework needed once its working
- Evaluation option to continue from random strategy [Think about this - not sure its necessary, problem is markov]
- Track action values and calculate how they diverge from theoretical ones [DONE]
- Investigate what this suboptimal strategy is that agents converge to [SEMI DONE]

#### Simulator Version 2
- Transition to Wandb:
	- test metric tracking
	- remove live plots
	- integrate agent hyperparameters
	- sweep integration


### Market Models and Environment
- Add new market models 
- Expand the feature set

### Reading
- Sutton and Barto (part 2)
- Next RL execution paper [DONE]
- Deep L in py book (buy)
- Double deep q paper [DONE]
- Prioritised replay
- Distributional approach
	- C51 [DONE]
	- IQN 
- Neural net papers / reading [PRIORITY]


#### Other Reading
- Restricted Boltzman machines [SCRAP]
- Random Forests [SCRAP]
- Target Networks [DONE]

### Writing
- Talk about DDQN in practise (halving epsilon decay?)
- Transformations of the features
- Case study on robustness and DDQ - could demonstate / prove the issues with the niave approach DQN
- How do we know when its converged outside of the simulated environment
- Semi Gradient decent discussion (convergence page 202 Sutton Barto)
- Distributional RL Theory

### Network Architecture
- Look at improving the architecture of the Neural Net

### General
- Need to cut down the number of training episodes:
	- pre training on simulated data?
	- Reuse training data
	- prioritised sweeping

### Data
- real_stock
	- option of reusing data or not (random sampling with replacement or without)
		- if reuse: start at random time
		- if not: split the data into n 1hr intervals

### Questions for Paul


Deep reinforcement learning hands on

### Paul Meeting 3
- Evaluation (run for 100 steps, evaluate for 40)
- Takes many episodes to converge (if ever) and limited data available
- C51
- QRDQN
- Wandb and performance
- Testing on data
- Temporary impact


## Simulator
- pretraining broken
- action value record probably broken (how is it still working?) [FIXED]
- multiple strategies broken [ABANDON]

## baseAgent
- tweaks to stock processing net

## distAgent
- clean up

## localEnvironment
- Needs standardising and cleaning - particularly state generation

## realStock
- partition training and testing data [DONE]

## General:
- overhaul time periods and standardise units of time
	- All time periods measured in seconds
		- Agent
		- Simulator
		- Market

## QRAgent:
	- Get working [DONE]
	- Cleanup






