
# Trip planning bot

Trip planning bot is a bot devised to help plan a tour including the flights to take, the hotels to stay at and the tourist places to visit in the destination city within available budget.     


## Workflow
The script will first ask for the budget and start and end cities as input. It will then use data stored in excels files to get the flight details from the start city to the end city. 

After subtracting the cost of flight from the budget, it will suggest tourist places and hotels in the end city available for the remaining budget. The script will use other excel files to get all the tourist places and hotels in the end city. It will then filter out all the tourist places and hotels that are above the remaining budget.

Finally, it will display all these hotels within budget along with suggested tourist places in the end city available for the remaining budget.

## Functions

###  main()
*The main function clearly defines the workflow of the whole script. It also takes input for `budget` from user.*

<br>

### give_flight_options()
*This function takes user input for starting and destination city and returns the same as two variables `user_location` and ` user_destination`.*

<br>

### get_flight_price(curr_budget)
 *This function gets flight price of the selected flight and changes the budget accordingly.*
>`curr_budget` is a variable maintained in the `main` function for the   budget available at the time of executing the function. 

<br>

### get_hotel_price(destination_city, curr_budget)
*This function displays  hotels available  at the current budget in the destination city for the user to choose one from. It returns the cost as the selected hotel as variable `price`.*
> `curr_budget` is a variable maintained in the `main` function for the   budget available at the time of executing the function.
`destination_city` is the end city defined by the user.

<br>

### get_place_price(destination_city, curr_budget)
*This function displays  tourist places available  at the current budget in the destination city for the user to choose one from. It returns the cost as the selected these places as variable `price`.*
> `curr_budget` is a variable maintained in the `main` function for the   budget available at the time of executing the function.
>`destination_city` is the end city defined by the user.

<br>

### budget_warning(problem)
*This function is called when expenses get larger than current budget . It restarts flow  from the `main` function*.
> `problem` is the expense that triggered the function.

<br>

### calc_budget(budget, cost)
*This is used to calculate budget when it is modified due to new expenses*
> `budget` is the current budget.
> `cost` is the expense that is to be subtracted from `budget`.

<br>

## Data
We use three excel files for the script:
1. flights.xlsx
2. hotels.xlsx
3. places.xlsx

<br>

**flights.xlsx** 
|  start | desination   | price   |
| ------------ | ------------ | ------------ |
|  starting city |destination city   |flight cost in rupees   |

**hotels.xlsx** 
|  city | hotel   | price   |
| ------------ | ------------ | ------------ |
|  destination city  |hotel name   |hotel cost in rupees   |

**places.xlsx** 
|  city | activities   | price   |
| ------------ | ------------ | ------------ |
|  destination city  |all activities in the city   |activity cost in rupees   |


## Dependancies
[Openpyxl v. 3.1.2](https://pypi.org/project/openpyxl/ "Openpyxl")
