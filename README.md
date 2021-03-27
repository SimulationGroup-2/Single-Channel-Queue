




## Single Channel Queue


<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## About The Project

[![Product Name Screen Shot][product-screenshot]](https://example.com)

There are many great README templates available on GitHub, however, I didn't find one that really suit my needs so I created this enhanced one. I want to create a README template so amazing that it'll be the last one you ever need -- I think this is it.

Here's why:
* Your time should be focused on creating something amazing. A project that solves a problem and helps others
* You shouldn't be doing the same tasks over and over like creating a README from scratch
* You should element DRY principles to the rest of your life :smile:

Of course, no one template will serve all projects since your needs may be different. So I'll be adding more in the near future. You may also suggest changes by forking this repo and creating a pull request or opening an issue. Thanks to all the people have have contributed to expanding this template!

A list of commonly used resources that I find helpful are listed in the acknowledgements.

### Built With

This section should list any major frameworks that you built your project using. Leave any add-ons/plugins for the acknowledgements section. Here are a few examples.
* [Bootstrap](https://getbootstrap.com)
* [JQuery](https://jquery.com)
* [Laravel](https://laravel.com)








## We are students of CSE!!

- 🔭 NAME:Debashis Das Joy      ID:CSE 01306122
- 👯 NAME:Subashis Roy Bhowmik  ID:CSE 01306114
- 🥅 NAME:Muntasir Ahmed        ID:CSE 01306090
- ⚡ NAME:Rifat Bin Anwar       ID:CSE 01306116
- ⚡ NAME:Pushpita Shil         ID:CSE 01306100



##**Single Channel Queue**##
So first we import scipy.stats package for importing necessary funtion.
Here we use Poisson and Exponential Distribution to generate interarrival time and service time respectively.
µ=5.6 customers/minute (arrival rate) λ=1 customers/minute (service rate) for 20 customers.

In Poisson Distribution,Poisson distribution is described in terms of the rate (μ) at which the events happen. 
An event can occur 0, 1, 2, … times in an interval. 
The average number of events in an interval is designated λ (lambda). Lambda is the event rate, also called the rate parameter.


In Exponential Distribution, we can generate an exponentially distributed random variable using scipy.stats module's expon.rvs() method which takes shape parameter scale as its argument which is nothing but 1/lambda in the equation. 
To shift distribution use the loc argument, size decides the number of random variates in the distribution.


So for Poisson Distribution we use mu=5.6 and size=19 .Because for the first customer interarrival time is always none(0) thats why we use size=19.
So for Exponential Distribution we use scale=1,loc=0,size=20.
Then we find the arrival time using the formula :current customer interarrival time + previous customer arrival time and implement it in a for loop.
Then we find out service time using Exponential Distribution using the above values.
For Time service begin time we use the formula : if (current customer arrival time < previous customer Time service Ends time ) then current customer Time service Begin time = previous customer Time service Ends time ELSE current customer arrival time.
For time service ends time we use we use the formula : current customer time service begin time + current custome service time.
For waiting time, using formula: if (current customer arrival time < previous customer time service ends time ) then Previous customer time service ends time - current customer arrival time ELSE "Zero".
Then finding the customer who wait by counting value of waiting time which is greater than "Zero".And implemented the logic in for loop.
For Time Customer Spends in System(min) = waiting time + service time and implemented the logic in for loop.
For idle time , we use formula: if (previous customer time service ends time < current customer arrival time ) then current customer arrival time - previous customer time service ends time ELSE "Zero".
Finally generating the whole single channel queue  table.
And also find out the Average number of customer waiting and Average waiting time for a customer.






