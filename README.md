## Single Channel Queue


<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#Requirements">Requirements</a></li>
      </ul>
    </li>
    <li>
      <a href="#introduction">Introduction</a>
      <ul>
        <li><a href="#random-variable">Random Variable</a></li>
        <li><a href="#single-channel-queuing-problems">Single Channel Queuing Problems</a></li>
        <li><a href="#poisson-arrivals">Poisson Arrivals</a></li>
        <li><a href="#exponential-service-times">Exponential Service Times</a></li>
        <li><a href="#mathematical-analysis">Mathematical Analysis</a></li>
      </ul>
    </li>
    <li><a href="#release-history">Release History</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## About The Project
The implementation of python projects deals with one problem of single-channel queuing problems. It shows that a single-channel queuing model without losses can be used to solve queuing problems. It is composed of the queue and service center and uses the FIFO system.A single-channel queue can be used for a bank system /ticket counter service/any delivery service.

### Requirements
The main requirements are listed below:
* [Python 3.6](https://www.python.org/)
* [Numpy](https://numpy.org/)
* [Scikit-Learn](https://scikit-learn.org/stable/)
* [Matplotlib](https://matplotlib.org/)
* [Pandas](https://pandas.pydata.org/)
* [Jupyter](https://jupyter.org/)

<!-- Introduction -->
## Introduction

To describe queuing problems through mathematical formulation, some assumptions are made by considering arrivals and services as patterned by known function. Equations representing the distribution of the time between arrivals are used with other equations depicting other features such as the distribution of the service time. The relationship existing between these equations is the matter studied in waiting line theory. Arrivals of people or entry requirements (events) are customarily Poisson distributed. The duration of the service provided by people is usually exponentially distributed. For generating interarrival and service times, gamma and Weibull distributions are also utilized depending on the model as the exponential distribution is said to be a special case of
both of the gamma and Weibull distributions.

### Random Variable

A random variable is a variable whose possible values are numerical outcomes of a random phenomenon. There are two types of random variables, discrete and continuous.

A discrete random variable may take on only a countable number of distinct values and thus can be quantified. For example, you can define a random variable X to be the number that comes up when you roll a fair dice. X can take values : [1,2,3,4,5,6] and therefore is a discrete random variable.

Some examples of discrete probability distributions are Bernoulli distribution, Binomial distribution, Poisson distribution, etc.

A continuous random variable takes an infinite number of possible values. For example, you can define a random variable X to be the height of students in a class. Since the continuous random variable is defined for values, it is represented by the area under a curve (or the integral).


A curve meeting needed requirements is often known as a density curve. Some examples of continuous probability distributions are normal distribution, exponential distribution, beta distribution, etc.

There’s another type of distribution that often pops up in literature which you should know about called cumulative distribution function. All random variables (discrete and continuous) have a cumulative distribution function. It is a function giving the probability that the random variable X is less than or equal to x, for every value x. For a discrete random variable, the cumulative distribution function is found by summing up the probabilities.

### Single Channel Queuing Problems
Single-station or single-channel queuing problem is the name applied to those problems in which only one unit (station) is delivering the service as illustrated in Fig, where circles represent the arrival elements (events) and a square represents a station which contains an element being serviced.



![image](https://user-images.githubusercontent.com/79735184/112728527-f3c79b80-8f51-11eb-9e06-38352dbb290f.png)



### Poisson Arrivals
The Poisson is a discrete probability distribution and yields the number of arrivals in a given time. The exponential distribution is a continuous function and yields the distribution of the time intervals between arrivals. The Poisson distribution considers the behavior of arrivals as occurring at random and postulates the presence of a constant “λ” which is independent of the time. The constant λ represents the mean arrival rate or the number of arrivals per unit of time, and λ 1 is the length of the time interval between two consecutive arrivals. 

### Exponential Service Times
In Exponential Distribution, we can generate an exponentially distributed random variable using scipy.stats module's expon.rvs() method which takes shape parameter scale as its argument which is nothing but 1/lambda in the equation. To shift distribution use the loc argument, size decides the number of random variates in the distribution.



### Mathematical Analysis
So first we import scipy.stats package for importing necessary function.
Here we use Poisson and Exponential Distribution to generate interarrival time and service time respectively.
µ=5.6 customers/minute (arrival rate) λ=1 customers/minute (service rate) for 20 customers.So for Poisson Distribution, we use mu=5.6 and size=19. Because for the first customer there is no interarrival time that's why we use size=19.So for Exponential Distribution we use scale=1,loc=0,size=20.
Then we find the arrival time using the formula: current customer interarrival time + previous customer arrival time and implement it in for a loop. Then we find out service time using Exponential Distribution using the above values. For Time service begin time we use the formula: if (current customer arrival time < previous customer Time service Ends time ) then current customer Time service Begin time = previous customer Time service Ends time ELSE current customer arrival time.
For time service ends time we use we use the formula: current customer time service begin time + current customer service time.
For waiting time, using the formula: if (current customer arrival time < previous customer time service ends time ) then Previous customer time service ends time - current customer arrival time ELSE "Zero".
Then finding the customer who waits by counting the value of waiting time which is greater than "Zero".And implemented the logic in for loop.
For Time Customer Spends in System(min) = waiting time + service time and implemented the logic in for loop. For an idle time, we use the formula: if (previous customer time service ends time < current customer arrival time ) then current customer arrival time - previous customer time service ends time ELSE there is no idle time".Finally generating the whole single-channel queue table. And also find out the average number of customer waiting and Average waiting time for a customer.

## Release History
* 0.1.0
    * CHANGE: Update readme and code`
* 0.0.1
    * Work in progress


<!-- CONTRIBUTING -->
## Contributing

- 🔭 NAME:Debashis Das Joy      ID:CSE 01306122
- 👯 NAME:Subashis Roy Bhowmik  ID:CSE 01306114
- 🥅 NAME:Muntasir Ahmed        ID:CSE 01306090
- ⚡ NAME:Rifat Bin Anwar       ID:CSE 01306116
- ⚡ NAME:Pushpita Shil         ID:CSE 01306100
<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.

