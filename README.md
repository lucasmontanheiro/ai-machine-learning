# machine-learning

## Introduction

Machines perform routine tasks at incredible speeds, but still require humans to do the actual thinking.

## Steps

*Problem → Create rule → Apply rule → Feedback → Adjust rule*

In ML, you don't create explicit rules. ML prepares you to perform math tasks associated with algorithms used in machine learning to make either predictions or classifications from your data. 

The fourth part of the book helps you discover what to do about data that isn’t quite up to par. This part is also where you start learning about similarity and working with linear models. 

The most advanced chapter tells you how to work with ensembles of learners to perform tasks that might not otherwise be reasonable to complete.

## Tribes

The five tribes are – 

- **Symbolists**: The origin of this tribe is in logic and philosophy. This group relies on inverse deduction to solve problems. Symbolic reasoning The term inverse deduction commonly appears as induction. In symbolic reasoning, deduction expands the realm of human knowledge, while induction raises the level of human knowledge. Induction commonly opens new fields of exploration, while deduction explores those fields. However, the most important consideration is that induction is the science portion of this type of reasoning, while deduction is the engineering. The two strategies work hand in hand to solve problems by first opening a field of potential exploration to solve the problem and then exploring that field to determine whether it does, in fact, solve it.

- **Connectionists**: The origin of this tribe is in neuroscience. This group relies on backpropagation to solve problems. As an example of this strategy, deduction would say that if a tree is green and green trees are alive, the tree must be alive. When thinking about induction, you would say that the tree is green and the tree is also alive; therefore, green trees are alive. Induction provides… Connections modelled on the brain’s neurons The connectionists are perhaps the most famous of the five tribes. This tribe strives to reproduce the brain’s functions using silicon instead of neurons. Essentially, each of the neurons (created as an algorithm that models the real-world counterpart) solves a small piece of… The use of backpropagation, or backward propagation of errors, seeks to determine the conditions under which errors are removed from networks built to resemble the human neurons by changing the weights (how much a particular input figures into the result) and biases (which features are selected) of the network. The goal is to continue changing the weights and biases until such time as the actual output matches the target output. At this point, the artificial neuron fires and passes its solution along to the next neuron in line. The solution created by just one neuron…

- **Evolutionaries**: The origin of this tribe is in evolutionary biology. This group relies on genetic programming to solve problems. Evolutionary algorithms that test variation The evolutionaries rely on the principles of evolution to solve problems. In other words, this strategy is based on the survival of the fittest (removing any solutions that don’t match the desired output). A fitness… Using a tree structure, the solution method looks for the best solution based on function output. The winner of each level of evolution gets to build the next-level functions. The idea is that the next level will get closer to solving the problem but may not solve it completely, which means that another level is needed. This particular tribe relies heavily on recursion and languages that strongly support recursion to solve problems. An interesting output…

- **Bayesians**: The origin of this tribe is in statistics. This group relies on probabilistic inference to solve problems. Bayesian inference The Bayesians use various statistical methods to solve problems. Given that statistical methods can create more than one apparently correct solution, the choice of a function becomes one of determining which function has the highest probability of succeeding. For example, when using these techniques, you can accept a set of symptoms as input and decide the probability that a particular disease will result from the symptoms as output. Given that multiple diseases have the same symptoms, the probability… Ultimately, this tribe supports the idea of never quite trusting any hypothesis (a result that someone has given you) completely without seeing the evidence used to make it (the input the other person used to make the hypothesis). Analyzing the evidence proves or disproves the hypothesis that it supports. Consequently, it isn’t possible to determine which disease someone has until…

- **Analogizers**: The origin of this tribe is in psychology. This group relies on kernel machines to solve problems. Systems that learn by analogy The analogyzers use kernel machines to recognize patterns in data. By recognizing the pattern of one set of inputs and comparing it to the pattern of a known output, you can create a problem solution. The goal is to use similarity to determine the best solution to a problem. It’s the kind of reasoning that… therefore, using that solution for a similar set of circumstances should also work. One of the most recognizable outputs from this tribe is recommender systems. For example, when you get on Amazon and buy a product, the recommender system comes...

## Different types of Machine Learning

### Supervised learning

Tutor show how to work and machine will replicate
Pros
Needs a knowledgeable tutor

- Labeled sample data: tagged with identifiable information
- Inputs: dependable variables
- Output: independable variables

Difference Between Independent and Dependent Variables in Machine Learning
Independent variables (also referred to as Features) are the input for a process that is being analyzes. Dependent variables are the output of the process.

#### Steps
1) Collect Training Data
2) Train Classifier
3) Make Predictions

This code represents the ML to tell the difference between Apples and Oranges. 

Training Data
| Weight | Texture | Label  |
|--------|---------|--------|
| 150g   | Bumpy   | Orange |
| 170g   | Bumpy   | Orange |
| 140g   | Smooth  | Apple  |
| 130g   | Smooth  | Apple  |

```
from sklearn import tree

# 0 is for Bumpy, 1 is for Smooth
features = [[140, 1], [130, 1], [150, 0], [170, 0]]

# 0 is for Apple, 1 is for Oranges
labels = [0, 0, 1, 1]

clf = tree.DecisionTreeClassifier()
clf = clf.fit(features, labels)

# Trying to predict if a 150g, Bumpy fruit if an Apple or an Orange 
print clf.predict([[150, 0]])
```

**You know a lot more about the data.**


### Unsupervised learning 

Machine will find patterns and learn

Pros
- Needs to watch a lot of data
- Needs to watch good data

Learning and improving by trial and error: unlabeled data
Use different algorithms to study and learn about the data

Output
- Multiclass Classification: several groups you want to classify your data

**You don't know about the data. Machine will create the clusters. Because of that, Unsupervised needs a massive amount of data.**


### Semi-supervised learning

Combination of both
Cross over about both types of data

Steps
- Supervised: Start a training set in order for machine to learn
- Unsupervised: Fit the machine to classify the rest (inductive reasoning)

Inductive and transductive reasoning leads to misleading data. 
- Transduction is reasoning from observed, specific (training) cases to specific (test) cases. In contrast, induction is reasoning from observed training cases to general rules, which are then applied to the test cases.

Reinforcement
Reinforcement learning lets the machine learn with inputs from the user towards the best strategy.

### Q learning
States = set environment
Actions = responses
Quality = Q

