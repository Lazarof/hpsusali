# hpsusali
***Proposal and discussion of the code system for HPS USALI***
=======================================
   
## The code is composed of 13 digits:

     H 0 0 0 0 - 0 0 0  0  -  0  0
     1 2 3 4 5 6 7 8 9 10 11 12 13
    
## the digits 2 3 4 5 represent the type of schedule according to usali

         0100 Rooms
         0200 Food and Beverage
         0300 Other Operated Departments
         0301 Golf Course and Pro Shop
         0302 Health Club/Spa
         0303 Parking
         0304 Transportation
         0305 Guest Laundry
         0306 Swimming Pool/Beach
         0307 Tennis and Pro Shop
         0308 Other Recreation
         0309 Business Center
         0310 Navy
         0311 Retail Store
         0312 Children's Camp
         0313 Barber/Beauty Shop
         0314 Mixed Ownership
         0315 Gaming
         0316 Minor Operated Departments
         0400 Miscellaneous Income
         0500 Administrative and General
         0600 Information and Telecommunication Systems
         0700 Sales and Marketing
         0800 Property Operation and Maintenance
         0900 Utilities
         1000 Management Fees
         1100 Non-Operating Income and Expenses
         1200 House Laundry
         1300 Staff Dining
         1400 Payroll-Related Expenses
         0000 Summary Operating Statement for Operators/Owners
         
## the digits 7 8 9 10 allow us to create a logical order within the type of schedule

        H0100-0200-00 Transient Rooms Revenue

        H0100-0202-01 Retail Room Revenue
        H0100-0204-01 Discount .Revenue
        H0100-0206-01 Negotiated R.Revenue
        H0100-0208-01 Reward Redemption

## the digits 12 13 visually define the data type

         00 - an informative line
         01 - a value obtained from the initial data.
         02 - a calculated value
         22 - total calculated value representing 100%

         04 - a calculated or obtained value that will be used as a global parameter at the start of all
             the schedules except in the type of schedule where it was defined (see digits 2 3 4 5)

 ##          For example, in schedule 0000 we define

                 H0000-0200-04 Rooms Occupied (Sold)

                 which is equal to

                 H0000-0200-02 Rooms Occupied (Sold)

                 but with 04,
                
                 H0000-0200-04 Rooms Occupied (Sold)
                
                 because it is 04 it will appear in the header of all schedules except 0000

##                 So we can define parameters that appear in all schedules
                     Rooms available
                     Occupation
                     ADR
                     Rooms RevPar
                     Total RevPar
