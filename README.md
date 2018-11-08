
# Introduction to Experimental Design

## Introduction

In this lesson, we'll learn about the importance of sound experimental design, and how it underpins every decision we make as Data Scientists!

## Objectives

You will be able to:

* Understand and explain the concepts behind sound experimental design. 
* Understand and explain the purpose of **_Control Groups_** in experiments
* Understand and explain how **_Random Controlled Trials_** work, and why randomness is important


##  Review: The Scientific Method

You probably remember at least a little bit about the **_Scientific Method_** from your time in school.  In this lesson, we'll focus on the thing that makes it work--sound experimental design! The scientific method has been responsible for all the great progress humanity has seen in everything from medicine to physics to electronics, all because scientists working on problems knew how to design experiments in a way that helped them answer important questions with as little ambiguity as possible. If the scientific method was a car, then experimental design would be the engine that allows that car to move. This is especially important to us as Data Scientists, because it allows us to examine any problem through the lens of the **_Null Hypothesis_**!

The general structure of an experiment is as follows:

### 1. Make an Observation

The first step of the scientific method is to observe something that we want to test. During this step, we observe phenomena to help us refine the question that we want to answer.  This might be anything from "does this drug have an affect on headaches?" to "does the color of this button affect the number of sales our website makes in a day?".  Before we can test these things, we need to notice they exist and then come up with a specific question to answer. 

### 2. Examine the Research

Good data scientists work smart before they work hard.  In the case of scientific method, this means seeing what research already exists that may help us answer our question, directly or indirectly.  It could be that someone else has already done an experiment that answers our question--if that's case, we should be aware of that experiment before starting our own, as it could inform our approach to structuring our experiment, or maybe even answer our question outright!  

### 3. Form a Hypothesis

This is the stage that most people remember from learning the scientific method in grade school. In school, we learned that a hypothesis is just an educated guess that we will try to prove by structuring our experiment. In reality, its a bit more complicated than that.  During this stage, we'll formulate 2 hypotheses to test--our educated guess about the outcome is called our **_Alternative Hypothesis_**, while the opposite of it is called the **_Null Hypothesis_**.  This is where the language behind experimental design (and the idea of what we can actually **_prove_** using an experiment) gets a bit complicated--more on this below. 

### 4. Conduct an Experiment

This step is the part of the scientific method that we're most concerned with for this section. We can only test our hypothesis by gathering data from a well-structured experiment.  A well-structured experiment means is one that accounts for all of the mistakes and randomness that could give us mistaken signals as to the effect an intervention has.  Just because we're running an experiment doesn't prove that A causes B, or that there's even a relationship between them! A poorly designed experiment will lead to false conclusions that we haven't considered or controlled for--a well-designed experiment leaves us no choice but to acknowledge that the effects seen in a dependent variable are related to our independent variable.  The world is messy and random--we have to account for this messiness and randomness in experiments, so that we can filter it out and be left only with the things we're actively trying to measure. 

### 5. Analyze Experimental Results

Whether you realize it or not, you've already gotten pretty good at this step! All the work we've done with statistics is usually in service of this goal--looking at the data and understanding what happened. During this step, we tease out relationships, filter out noise, and try to determine if something that happened is **_statistically significant_** or not. 

### 6. Draw Conclusions

This step is the logical end point for our experiment.  We've asked a question, looked at experimental results from others that could be related to our question, made an educated guess, designed an experiment, collected data and analyzed the results.  All that is left is to use the results of our analysis step to evaluate whether we believe our hypothesis was correct or not! While the public generally oversimplifies this step to determining causal relationships (e.g. "my experiment showed that {x} causes {y}"), true scientists rarely make claims so bold.  The reality of this step is that we use our analysis of the data to do one of two things: either **_reject the null hypothesis, or fail to reject the null hypothesis_**.  This is a tricky concept, so we'll explore it in much more detail in a future lesson. 


<img src='The+Scientific+Method.jpg' height=50% width=50%>

## The Foundations of a Sound Experiment

All experiments are not created equal--simply following the steps outlined above does not guarantee that the results of any experiment will be meaningful. For instance, there's nothing stopping a person from testing the hypothesis that "wearing a green shirt will make it rain tomorrow!", seeing rain the next day, and rejecting the null hypothesis, thereby incorrectly "proving" that their choice of wardrobe affected the weather.  Good experiments show us that our independent variable {X} has an affect on our dependent variable {Y} because we control for all the other things that could be affecting {Y}, until we are forced to conclude that the only thing that explains what happened to {Y} is {X}!

Although there are many different kinds of experiments, there are some fundamental aspects of experimental design that all experiments have:

### 1. A Control Group/Random Controlled Trials

One of the most important aspects of a sound experiment is the use of a **_Control Group_**. A Control Group is a cohort that receives no treatment or intervention--for them, it's just business as usual.  In a medical test, this might be a **_placebo_**, such as a sugar pill. In the example of testing the color of a button on a website, this would be customers that are shown the a version of the website with the button color unchanged.  Using a control group allows us to compare the results of doing nothing (our control) with the effects  of doing something (our **_intervention_**).  Without a control group, we have no way of knowing how much of the results we see can be attributed to our intervention, and how much would have happened anyways. 

To make this more obvious, let's consider what we can actually know with confidence after an experiment that doesn't use a control. Let's say that a pharmaceutical company decides to test a new drug that is supposed to reduce the amount of time someone has the flu.  The company gives the drug to all participants in the study.  After analyzing the data, we find that the average length of time a person had the flu was 12 days.  Was the drug effective, or not? Without a control, we don't know how long this flu would have lasted if these people were never given a drug.  It could be that our drug reduced the time of infection down to 12 days.  Then again, it could be that the these people would have gotten better on their own after 12 days, and our drug didn't really do anything--or maybe they would have gotten better in 10 days, and our drug made it worse! By using a control group that gets no drugs and recovers naturally, we can compare the results of our treatment (people that received the experimental flu drug) to our control group (people that recovered naturally).

Note that a control group is only a control group if they are sampled from the same population as our treatment groups! If they aren't the same, then we have no way of knowing how much of the difference between in results should be attributed to our flu drug, and how much should be attributed to the way(s) in which the control group is different.  For instance, our experiment would not be very effective if the average age of one group was much higher or lower than another--if that was the case, how do we know the age difference isn't actually causing the difference in results (or lack thereof) between our control and our treatment groups, instead of our drug?

The main way scientists deal with this is through **_Random Controlled Trials_**.  In a Random Controlled Trial, we have a control group and an intervention (also called treatment) group, where subjects are **_randomly assigned to each_**.  You may have heard the term **_Single-Blind_** and **_Double-Blind_**--these refer to people knowing which groups they are in. In a sound experiment, people should not know if they are in the treatment group or the control group, as that could potentially affect the outcome of the trial! 

A **_Single-Blind_** or **_Blind Trial_** is one where the participant does not know if they are receiving the treatment or a placebo. 

A **_Double-Blind Trial_** is one where the participant does not know if they are receiving the treatment or a placebo, and neither does the person administering the experiment (because their bias could affect the outcomes, too!).  Instead, knowing whether someone received the treatment or a placebo is kept hidden from everyone until after the experiment is over (obviously, _someone_ has to know for recordkeeping purposes, but that person stays away from the actual experiment to avoid contaminating it with bias from that knowledge). 

<img src='double_blind.png' height=40% width=40%>

### 2. Appropriate Sample Sizes

Randomness is a big problem in experiments--it can lead us to false conclusions by making us think that something doesn't matter when it does, or vice versa. Small sample sizes make us susceptible to the problem of randomness. Large sample sizes protect us from it.  The following scenario illustrates this point:

A person tells you that they can predict the outcome of a fair coin flip. You flip a coin, they call "tails", and they are correct.  Is this enough evidence to accept or reject this person's statement?  What if they got it right 2 times in a row? 5 times in a row? 55 times out of 100?  

This situation illustrates two things that are important for us to understand and acknowledge:

1. No matter how large your sample size, there's always a chance that our results can be attributed to randomness or luck.

1. At some point, we cross a threshold where random chance is small enough that we say "this probably isn't random", and are okay with accepting the results as the result of something other than randomness or luck.

With the situation above, we probably wouldn't assume that this person can predict coin flips after only seeing them get 1 correct.  However, if this person got 970 out of 1000 correct, we probably believe very strongly that this person _can_ predict coin flips, because the odds of guessing randomly and getting 970/1000 correct are very, very small--but not 0!  

Large sample sizes protect us from randomness and variance. A more realistic example would be testing a treatment for HIV.  Less than 1% of the global population carry a protective mutation that makes them resistant to HIV infection.  If our sample size is only 1 person randomly selected from the population, there is a ~1% chance that we may mistakenly attribute successful prevention to the drug we're testing, when the results really happened because we randomly selected a person with this mutation.  However, if our sample size is 100 people per sample, our odds of randomly selecting 100 people with that mutation are $.01^100$. The larger our sample size, the more unlikely it is that we randomly draw people that happen to affect our study.

<img src='sample_size.jpg' height=40% width=40%>


### 3. Reproducibility

This one is a big one, and is a bit of a crisis in some parts of the scientific community right now.  Good scientific experiments have **_Reproducible Results_**! This means that if someone else follows the steps you outline for your experiment and performs it themselves, they should get pretty much the same results as you did (allowing for natural variance and randomness). If many different people try reproducing your experiment and don't get the same results, this might suggest that your results may be due to randomness, or to a **_lurking variable_** that was present in your samples that wasn't present in others. Either way, lack of reproducibility often casts serious doubts on the results of a study or experiment. 

This is less of a problem for data scientists, since reproducibility for us usually just means providing the dataset we worked with and the corresponding jupyter notebook.  However, this isn't always the case!   Luckily, we can use code to easily run our experiments multiple times and show reproducibility. When planning experiments, consider running them multiple times to ensure to really help show that your results are sound, and not due to randomness!

## Summary

Great, you now know about experimental design and the fundamental aspects of experiments! 
