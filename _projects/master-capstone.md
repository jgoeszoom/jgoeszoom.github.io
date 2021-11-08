---
layout: project
title: "Phasor Measurment Unit for Master's Capstone Project"
proj-link: https://drive.google.com/file/d/1H_6r5RlxIflFqnsv3yq6OhnptZTSkAKW/view?usp=sharing
desc: "3-phase power signals spread by 120 degrees apart"
img: "3P-power.jpg"
---

## By Joseph Gozum

## Problem 
The U.S. Electrical Grid is aging, and with that comes the probablity of increased failure. So, aside from redoing the whole grid and working with what's already there, we can ensure reliablity and production as best we can. However, there's one problem. Often times a problem in the grid isn't an isolated problem and often times indicates a much larger issue. 

So what engineers have created are phasor measurement units (PMUs) which calculate synchrophasors. What these are are phasors that are sampled/calculated at a very precise and consistent time between phasors. If you have these placed throughout a grid, you can have wide-area awareness and more easily isolate the sources of problems and possibly identify them. 

But the biggest problem that faces there truly widespread rollout is cost, their production, installation, and maintence are big inhibitors. The U.S. government has provided grants and programs to help ease these issues. 

## Solution
What I proposed to do is to create a PMU using off-the-shelf components that can be readily and quickly integrated to calculate and report the synchrophasors. Trying to address the large cost mainly associated with production. 

## Results
I did end up creating the PMU using some components that I purchased from electronics vendors and the overall concept works but not without errors. The input signal is not consistently sampled, the clock that controls when an ADC samples the input electrical signal is not always properly aligned. With PMUs, the clock is aligned to the tick of a second with reference to UTC time. Sampling is also not truly parallel as it should be, unfortunately the signal is sampled sequentially across three different ADC inputs. In the future, I would love to address these issues but due to my time constraint this was not possible during my project time. 

Take a look at the link to my report if you want to know more at the top of the page below the titel!