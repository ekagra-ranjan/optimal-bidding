<h1 align="center">
Optimal Bidding
</h1>

<h2 align="center">
Inter IIT Techmeet 2017, IIT Madras - Data Science Competition
</h2>

<p align="center">
  <a href="https://github.com/ekagra-ranjan/Optimal-Bidding/"><img src="http://img.shields.io/badge/Public LB Rank-1-blue.svg"></a>
  <a href="https://github.com/ekagra-ranjan/Optimal-Bidding/"><img src="http://img.shields.io/badge/Private LB Rank-4-blue.svg"></a>
    <a href="https://github.com/ekagra-ranjan/Optimal-Bidding/raw/master/Method_Presentation_IIT_GUWAHATI.pptx"><img src="http://img.shields.io/badge/Slides-ppt-orange.svg"></a>
</p>

<br>
<br>

## Preamble to the Problem:
Liberalization of sale of electricity has led to competitive electricity markets. Generators and
consumers can trade electricity at prices agreeable to both by bidding in the market, which is
facilitated by market operators. Market operators ensure fair trade, reliable exchange of
electricity and money, and determine the market prices based on bids submitted.
There are various types of trading markets which exist but ‘Day Ahead Market’ (DAM) is of our
interest in this problem. In DAM, bidding happens a day ahead to the delivery of electricity. The
day of delivery is divided into multiple blocks of equal duration and for each of the blocks,
bidding happens separately and market prices are determined independently. A ‘bid’ includes a
price as well as a quantity (energy in of KWh). Eg. A consumer bids 100 units at Rs.5 per unit
which means that he is willing to buy 100 units of electricity at a cost less than or equal to five
rupees. If the market price turns out to be less than Rs.5, the consumer wins the bid, otherwise he
loses. The winning consumer is delivered the energy he bids, during particular block duration.
The market prices are determined by an algorithm which finds market prices based on
equilibrium in the bid quantities and bid prices submitted by the generators and consumers. It
also ensures that the there is no congestion in the lines for supply of electricity. Once the market
prices are determined, the bidders are informed whether they won the bid or not and what the
unit price is. For each block, the market price is same for all the members (non-discriminatory)
who win the bid, in a given region. The bid winning consumers have to pay for complete bid
quantity at the bid price irrespective of consumption and this cost gets added to his bill. The
losing consumers get no electricity from the market.
## Problem Statement:
Consider a scenario of a gated community with many buildings requiring electricity and a solar
panel plant installed along with a battery. The community decides to participate in the electricity
bidding market in their region. The community also has the option of drawing from a distribution
company (DISCOM) at a fixed per unit (KWh) cost. So there are four sources from which the
demand can be fulfilled viz. solar plant, battery, electricity market and DISCOM.
For the above defined scenario, formulate and develop an algorithm to solve the optimization
problem with an objective to minimize the daily electricity bill of the community as a whole. The
bid quantities and bid prices for each of the blocks are the decision variables of the optimization
problem.
Since bidding happens a day ahead, the actual electricity demand of the community and the
actual output of the solar plant are not known exactly. So a forecast of these quantities for each
of the blocks is given by an oracle at the time of bidding. A forecast of the most probable market
price for each of the blocks is given by the oracle at the time of bidding.
The problem formulation and solution should satisfy the constraints and make assumptions as
given in the following sections.
## Problem Constraints:
1. The actual demand of all the consumers should be fulfilled at any cost from one of the
four sources
2. Precedence of sources to fulfil demand: Solar plant > Electricity from market > Battery >
DISCOM
3. Battery has certain efficiency, a limited charging and discharging capacity (specified in
the data sheet)
4. Bid quantities should be only integers while bid price can take any value
## Problem Assumptions:
1. Battery can charge to its full capacity and discharge to zero state of charge
2. Battery can either charge or discharge in a given block but cannot do both and everything
is represented in terms of KWh for convenience
3. In a block, battery charges automatically when the supply from solar plant and electricity
market combined exceeds the demand
4. In a block, battery discharges automatically when the demand exceeds the supply from
solar plant and electricity market combined
5. The efficiency of the battery and inverter do not decrease with time
6. The capital costs and maintenance costs associated with solar plant, battery and inverter
are ignored. Hence the unit cost of electricity from solar plant is taken as zero
7. There are no upper and lower limits on the bid quantity
8. The market is large enough such that the effect of the bid made by the community, on the
market prices is negligible
9. The daily bill is calculated only based on energy purchased in units and per unit cost. All
other charges involved are ignored
## Expected Outputs:
Training and test sets are given separately for the problem. Training set includes predictions and
actual values of demand, solar output and market prices while the test set only has the
predictions. The teams have to develop an algorithm or an agent which outputs the optimal bid
quantity and price for each of the blocks in the day. The training set can be used by the teams in
any manner they deem necessary to develop and validate their algorithms. The final evaluation
will be based only on the output of the algorithm to the test set.
## Judging Criteria:
Leaderboard dataset includes data for 50 days.
Private dataset includes data for 100 days.
Score for a dataset = (Best Average for the period)/(Your Average for the period) * 100
Final Score = 10+0.9*( 0.2*Public-LeaderBoard-Set-Score + 0.8*Private-Test-Set-Score).
The 10 marks is given for presentation quality during Inter-IIT Tech Meet.
To make a leaderboard submission, refer to the leaderboard results page to find your institute
code.
If your institute code is 15 - Submit one csv file “15.csv”.
Solution has 2 columns and (50*24 = 1200 rows). Each row has hourwise bid-price in column1
and bid-quantities in column 2.
Once you submit refer to the leaderboard results.csv file to check your average price obtained
and similarly for other teams. ( Only best submissions are considered. -1 = No Submissions ).
## Data Sheet:
### Parameters to be used in the problem:
1. No of blocks in a day for bidding – 24 blocks each of duration one hour
2. Battery capacity – 25 KWh
3. Battery charging and discharging capacity – 5 KWh i,e,. battery can charge or discharge
in energy upto 5 KWh in an hour
4. Battery efficiency – 80% i,e,. if 10 KWh is stored in the battery, it can supply only 8
KWh
5. Inverter efficiency – 100%
6. Price of electricity offered by DISCOM – Rs.7/KWh
### Training Set:
1. Oracle predictions of the community’s hourly energy demand (in KWh) for 900 days are
available at Demand_Train_pred.csv
2. Oracle predictions of the hourly solar plant output (in KWh) for 900 days are available at
Solar_Train_pred.csv
3. Oracle predictions regional market prices (in Rs./KWh) for 900 days are available at
Price_Train_pred.csv
4. Actual values of the community’s hourly energy demand (in KWh) for 900 days are
available at Demand_Train.csv
5. Actual values of the hourly solar plant output (in KWh) for 900 days are available at
Solar_Train.csv
6. Actual values regional market prices (in Rs./KWh) for 900 days are available at
Price_Train.csv
### Public Leaderboard Set:
1. Oracle predictions of the community’s hourly energy demand (in KWh) for 50 days are
available at demand.csv
2. Oracle predictions of the hourly solar plant output (in KWh) for 50 days are available at
solar.csv.
3. Oracle predictions regional market prices (in Rs./KWh) for 50 days are available at
price.csv.


<br>
<br>

## Github repos of similar Data Science Competitions:

* [Analyze-This-18](https://github.com/ekagra-ranjan/Analyze-This-18)
* [Analyze-This-17](https://github.com/ekagra-ranjan/Analyze-This-17)
* [GS-Quantify-17](https://github.com/ekagra-ranjan/GS-Quantify-17/)
* [awesome-undergrad-hackathons](https://github.com/ekagra-ranjan/awesome-undergrad-hackathons)

<p align="center">
	Please star the repo if you found the materials in the repo useful :)
</p>
