# SharkLine Bets
slb.sharklinesports.com

## 1. About SLB and Framework

### Subset of SharkLineSports specifically focused on helping average, everyday sports wagerers create a portfolio geared towards identifying their betting trends based on a variety of data metrics. Users can take the aggregated data retrieved from their sports betting platform(s) and tailor queries they would like to run in order to see certain results. The SharkLine algorithm will provide users with a specific type of quality score combining factors such as Risk, Units, Outcome, Profit, Consistency.

Example: As a user, if I wanted to query results for the following:
  1. Straight Bets placed on the spread
  2. In NFL and College Football
  3. In the months of November and December

I could simply input the primary set of data I want to query for, and when the query is run, it will produce a table of informative information based off of the request such as Total Profit/Loss, Average Unit Bet, Teams Bet and many other customizable categories of data you may want to see.

In addition, it will provide users with a SharklineBet Score which can be custom to that specific query as well as a global SharkLine Bet Score which will include all data. 
  
 **User-Based Organizations**: 
  - Set up company-based organizations, allowing data to be isolated by role-based access.
  - Ability to invite and add other users to manage the data.

**Views within Application**:
  - Index - Profile page containing basic user info, integration for various betting apps, users specified Risk Tolerance Level, Current Global Sharkline Bet Score and Goals
  - Data Import - This page will contain the "SYNC" button to call external app API's and update with new data - This will also contain the manual data entry
  - Analytics Page -  Dashboards with high level overview user betting statistics and profit/loss, trends, pivot reports
  - Parlay Odds Calculator
  - Global Market Trends *Phase II
  - Sports News Alerts *Phase II
  - Pricing Plans & Upgrades
  - DFS *Phase II

## 2. Profile 

A users profile will be tailored towards their unique history, strategies and goals.

The SLB Score will dynamically update


## 3. Data Categories to be Aggregated

- **Single Collection**: Store all betting history in a single collection with each entry containing a unique `consumer_id`
- **Indexing**: Use `consumer_id` for indexing. 

**Data to Store**: When retrieving data from various API's the application will store the following review details (does not include granular subset details of each Category):
  - Name of Betting App(s) each data set is being pulled from
  - Sport(s)
  - Amount of money bet
  - Total Bankroll
  - Type of Bet (signified with tags)
    -Straight
      -MoneyLine
      -Spread
      -Over/Under
    -Parlay
      -Number of Legs
      -Types of Bet included in the Parlay
    -Teaser
      -Type of Teaser
    -Props
  -DFS (Daily Fantasy Sports)

**Outcome Data**
-COUNT(total_bets)
  COUNT(sport,type_of_bet,win,push,loss)
-SUM(total_bets)
  SUM(profit)
-AVG(total_bets,units,bet_by_sport,bet_by_type,wins,loss,push)

### Filters
1. Date Range
2. Sport
3. Type of Bet
4. Range of Odds (or operator - ( '>=' '<=' '>' '<' )


## 4. SLB Scoring System 
**Algorithm**
1. Provide weights to the following categories
     a. Odds (+/-) 
     b. Overall Profit/Loss
     c. Units won/lost
     d. Previous Betting Trend
     e. Number of bets placed
     f. Proximity of winning (If Loss)
     g. Risk level of type of bet (Moneyline Favored = 1, Moneyline Underdog =3, Straight Bet Spread = 2, Over/Under = 2, Teaser = 3, Parlay = 5)
2. Weights will be generated on a 0-100 integer scale
3. Global real-time SLB score which takes into account all data entered
4. Date-Filtered SLB score (filter by date)


   
## 5. Applications pulling user data from

Reference: FantasyPros.com performs a similar function in that they simply pull in the data directly from sites such as ESPN, Yahoo, Sleeper App, etc.. - You can also manually input data.

SYNC button will call the API's for all successfully integrated exteral applications.  

Historical Data Import - This will need to be pulled from a date range

**Popular External Betting Applications**

### DraftKings  
### FanDuel
### PrizePicks
### HardRock
### BetMGM
### Fanatics
### ESPN Bet

### Manual Import of Data

Manual Import will be structured as "groups" to provide a better user experience when entering multiple bets in a single instance.  require users to enter in the following information:

1. Application bet was placed on
2. Date the bet was placed
3. Type of Bet
4. Odds at time of placing wager
5. Total Bankroll at time of group entry (multiple bets can be added in a single entry and users will enter their total bankroll at the time of first bet of the group - If uesrs enter in bets in multiple "groups" they will need to enter in correct bankroll for each individual group)
6. Outcome Data (For historical data only)
   

## 6. API for Saving Data

- **API Endpoint**: Create an API to save betting history into a MongoDB collection.
- **Data to Pull**: Integrations with multiple popular sports betting applications 
 

## 7. Categories and Analysis (AI-Powered)

- **Category Collection**: Create a MongoDB collection for categories. Each category will store data points relevant to the category.
- **Insights**: Calculate Market trends and compare against user profile


## 8. Pricing Model

**Freemium Pricing Structure Hybrid**

Subcription Tiered Model for Premium Services with Annual Subscription discount and monthly option 
  Basic - Free
  SharkPro - Tier 1
  SharkPlatinum - Tier 2 


## 9. Email Integration

- **Email Functionality**: Use SendGrid or a similar service for functions like "forgot my password", "verify email", and "invite users".
- **Sentiment Alerts**: Daily alerts and news 
___

## 10. Monetization

1. Shark Pro and SharkPlatinum Accounts
2. Affiliate Sportsbook Referrals


# Tech Stack

## Frontend 
  Angular or React

## Backend
  Node.js

## Infracture
  AWS

## DB Storage
  MongoDB
