# Calendar-JAVA
how to make a calendar using two inputs, year and the first day of the year.

int Y = 2016;    // year
        int startDayOfMonth = 5;
        int spaces = startSayOfMonth;

        //months[i] = name of month i
        
        String[] months = {
                "",                                                                     // leave empty so that we start with months[1] = "January"
                "January", "February", "March",
                "April", "May", "June",
                "July", "August", "September",
                "October", "November", "December"
            };

            
            int[] days = {                                                              // days[i] = number of days in month i
                0, 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31
            };



            for (int M = 1; M <= 12; M++) {                                             //loop for month

            // check for leap year
            if  ((((Y % 4 == 0) && (Y % 100 != 0)) ||  (Y % 400 == 0)) && M == 2)       //if leap year change february to 29 days
                days[M] = 29;


            // print calendar header
            // Display the month and year
            System.out.println("          "+ months[M] + " " + Y);                      //title of month and year

            // Display the lines
            System.out.println("_____________________________________");                //calendar aesthetics
            System.out.println("   Sun  Mon Tue   Wed Thu   Fri  Sat");

            // spaces required                                                          //spaces u need for the gap before the month starts
               spaces = (days[M-1] + spaces)%7;                                         
                                                                                            /*the spaces depends on the month sebelum punya baki hari on 
                                                                                            the last   week + the spaces from months before /7 for the days in a week */



            // print the calendar
            for (int i = 0; i < spaces; i++)
                System.out.print("     ");                                              //printing out the spaces first



            for (int i = 1; i <= days[M]; i++) {
                System.out.printf(" %3d ", i);                                          //print the dates of the monthe
                if (((i + spaces) % 7 == 0) || (i == days[M])) System.out.println();    //if one line has 7 days or end of month , move to next line
            }

            System.out.println();
