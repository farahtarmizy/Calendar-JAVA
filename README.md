# Calendar-JAVA
how to make a calendar using two inputs, year and the first day of the year.

        System.out.println("Enter year: ");
        int year=s.nextInt();                                                                                            //ask user for year
        System.out.println("Enter first day of year: ");
        int start=s.nextInt();                                                                                           //ask user for first day of year 0-sundat, 1-monday...
        
        int spaces = start;
        
        String[] MonthName = {"","January", "February", "March",
                              "April", "May", "June", "July", "August", 
                              "September","October","November", "December"};                                             //setting names of month 
        
        
        int[] days = {0,30,29,30,31,
                      30,31,30,31,30,
                      31,30,31};                                                                                         //setting number of days in a month
       
        for(int Month=1; Month<=12; Month++){
            
            if(((year % 4 == 0) && (year % 100 != 0)) ||  (year % 400 == 0)&&(Month==2)){                                //check if it is loop year, if yes then feb has 29 days
                days[2]=29;
            }
            
            System.out.println("           "+MonthName[Month]+" "+year);
            System.out.println("____________________________________");
            System.out.println("  Sun  Mon  Tue  Wed  Thu  Fri  Sat");                                                   //header for the calendar
            
            
            spaces= (days[Month-1]+spaces)%7;                                                                           //spaces for the start of the month
                                                                                                                        //according to the day the year starts
            for(int i=0;i<spaces;i++){                                                                                   
                System.out.print("     ");                                                                              //print out the spaces 
            }
            
            
            for(int j=1;j<=days[Month];j++){
                
                System.out.printf("  %3d", j);                                                                          //print out the dates
                
                if(((j + spaces) % 7 == 0) || (j == days[Month]))
                    System.out.println();                                                                               //print new line if one line reaches 7 dates+spaces
                     
            }
            
            System.out.println();                                                                                       //new line for next month 
        }
