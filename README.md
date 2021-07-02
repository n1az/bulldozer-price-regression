# Predicting the Sale Price of Bulldozers using Machine Learning

In this notebook, we're goint to go through an example machine learning projects with the goal of predicting the sale price of bulldozers.

## 1. Problem definition

> How well can we predict the future sale price of a bulldozer, given its characterisitics and previous examples of how much similar bulldozers have been sold for?

## 2. Data

The data is downloaded from the Kaggle Bluebook for Bulldozers competition:

There are three main datasets:

* Train.csv is the training set, which contains data through the end of 2011.
* Valid.csv is the validation set, which contains data from January 1, 2012 - April 30, 2012 You make predictions on this set throughout the majority of the competition. Your score on this set is used to create the public leaderboard.
* Test.csv is the test set, which won't be released until the last week of the competition. It contains data from May 1, 2012 - November 2012. Your score on the test set determines your final rank for the competition.

## 3. Evaluation

The evaluation metric for this competition is the `RMSLE` (root mean squared log error) between the actual and predicted auction prices.

For more on the evaluation of this project check: https://www.kaggle.com/c/bluebook-for-bulldozers/overview/evaluation

**Note: The goal for most regression evaluation metrics is to minimize the error. For example, our goal for this project will be to build a machine learning model which minimised RMSLE.**

## 4. Features

Kaggle provides a data dictionary detailing all of the features of the dataset. You can view this data dictionary here:

* SalesID - unique identifier of a particular sale of a machine at auction
* MachineID - identifier for a particular machine; machines may have multiple sales
* ModelID - identifier for a unique machine model (i.e. fiModelDesc)
* datasource - source of the sale record; some sources are more diligent about reporting attributes of the machi...
* auctioneerID - identifier of a particular auctioneer, i.e. company that sold the machine at auction. Not the sam...
* YearMade - year of manufacturer of the Machine
* MachineHoursCurrentMeter - current usage of the machine in hours at time of sale (saledate); null or 0 means no hours have b...
* UsageBand - value (low, medium, high) calculated comparing this particular Machine-Sale hours to average usage...
* Saledate - time of sale
* Saleprice - cost of sale in USD
* fiModelDesc - Description of a unique machine model (see ModelID); concatenation of fiBaseModel & fiSecondaryDes...
* fiBaseModel - disaggregation of fiModelDesc
* fiSecondaryDesc - disaggregation of fiModelDesc
* fiModelSeries - disaggregation of fiModelDesc
* fiModelDescriptor - disaggregation of fiModelDesc
* ProductSize - Don't know what this is (The size class grouping for a product group. Subsets within product group.)
* ProductClassDesc - description of 2nd level hierarchical grouping (below ProductGroup) of fiModelDesc
* State - US State in which sale occurred
* ProductGroup - identifier for top-level hierarchical grouping of fiModelDesc
* ProductGroupDesc - description of top-level hierarchical grouping of fiModelDesc
* Drive_System - machine configuration; typcially describes whether 2 or 4 wheel drive
* Enclosure - machine configuration - does machine have an enclosed cab or not
* Forks - machine configuration - attachment used for lifting
* Pad_Type - machine configuration - type of treads a crawler machine uses
* Ride_Control - machine configuration - optional feature on loaders to make the ride smoother
* Stick - machine configuration - type of control
* Transmission - machine configuration - describes type of transmission; typically automatic or manual
* Turbocharged - machine configuration - engine naturally aspirated or turbocharged
* Blade_Extension - machine configuration - extension of standard blade
* Blade_Width - machine configuration - width of blade
* Enclosure_Type - machine configuration - does machine have an enclosed cab or not
* Engine_Horsepower - machine configuration - engine horsepower rating
* Hydraulics - machine configuration - type of hydraulics
* Pushblock - machine configuration - option
* Ripper - machine configuration - implement attached to machine to till soil
* Scarifier - machine configuration - implement attached to machine to condition soil
* Tip_control - machine configuration - type of blade control
* Tire_Size - machine configuration - size of primary tires
* Coupler - machine configuration - type of implement interface
* Coupler_System - machine configuration - type of implement interface
* Grouser_Tracks - machine configuration - describes ground contact interface
* Hydraulics_Flow - machine configuration - normal or high flow hydraulic system
* Track_Type - machine configuration - type of treads a crawler machine uses
* Undercarriage_Pad_Width - machine configuration - width of crawler treads
* Stick_Length - machine configuration - length of machine digging implement
* Thumb - machine configuration - attachment used for grabbing
* Pattern_Changer - machine configuration - can adjust the operator control configuration to suit the user
* Grouser_Type - machine configuration - type of treads a crawler machine uses
* Backhoe_Mounting - machine configuration - optional interface used to add a backhoe attachment
* Blade_Type - machine configuration - describes type of blade
* Travel_Controls - machine configuration - describes operator control configuration
* Differential_Type - machine configuration - differential type, typically locking or standard
* Steering_Controls - machine configuration - describes operator control configuration

### Tools

* Scikit-Learn
* Pandas
* Matplotlib
* NumPy
* Jupyter Notebook
* Anaconda