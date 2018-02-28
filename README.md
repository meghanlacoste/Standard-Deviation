# Standard-Deviation
package com.company;

import java.io.File;
import java.util.Scanner;

import static com.company.ProjConstants.*;

public class Main {

    public static void main(String[] args) {

        StDeviation calcSDev =  new StDeviation();

        String userFileName;

        System.out.println("");
        System.out.println("Please type in the file name\n");

        // create a variable s of type scanner to process input from "System.in"
        Scanner scanSystemIn = new Scanner(System.in);

        // Use the Scanner "s" to get the "next" input from "System.in"
        userFileName = scanSystemIn.next();


        File userFile = new File("tempfilenums.txt");
        Scanner scanUserFile = new Scanner("tempfilenums.txt");

        // Display the user input now stored in "userInput"
        System.out.println("\nThe user input: " + userFileName);


        int  someInteger=  0; // this should be a value taken from the file
        double theAverage = 0; // this is a result from method
        double theVariance = 0; // this is a result from method
        double theStDeviation = 0; // this is a result from method

            try {
                // Read in values from the file in a for loop

                for(int someInteger=0; someInteger < MAXDATA; someInteger++) {


                    if (scanUserFile.hasNext()) {
                        someInteger = scanUserFile.nextInt();
                        System.out.print(" - " + someInteger);

                        calcSDev.addNewDataItem(someInteger);

                        // ... calculate the average (see example)
                        theAverage = calcSDev.calcAverage();


                        // ... calculate the variance (see website)
                        theVariance = calcSDev.calcVariance();


                        // ... calculate the standard deviation (square root of variance ... java math library)
                        theStDeviation = calcSDev.calcStandardDeviation();


                        System.out.println("==================================================================\n");
                        System.out.printf("The Average is: " + theAverage);
                        System.out.printf("The Variance is: " + theVariance);
                        System.out.printf("The Standard Deviation is: " + theStDeviation);
                        System.out.println("==================================================================\n");

                    }// end if

                    else {
                        // ---------------------------------------------
                        // The scanner detected no other integers
                        // - closes the scanner for the file
                        // - breaks out of the for loop
                        //
                        System.out.println("==================================================================\n");
                        System.out.print("\n\nDataFileFILE has been completely READ");
                        scanUserFile.close();
                        System.out.println("==================================================================\n");

                        break;
                    }// end else
                }//end for

                System.out.println();

                // ---------------------------------------------
                // If the file cannot be found then an exception (error) is generated (thrown) that we have to
                // deal with (catch).
                // - we print "e" the exception, and
                // - show the user where it was using the "exceptions" stack trace information
                //

            } catch (FileNotFoundException e) {
                System.out.println(e);
                e.printStackTrace();
            }

            System.out.println("------------------------------------------------");







            //- Prompt User for file name
            // -> if the file exists then prepare to read the data using the StDeviation methods
            // ->: read the data from the file in a loop
            //  ** add data item into data set using Standard Deviation Method to add data


            //  ->: if the data file was not read completely then display warning to user and continue
            // -> if the file does not exist exit the program
            // LOOP TO READ FILE

            // ADD FILE TO ARRAY

            // END OF FILE OR DATA IMPut



            //display all information neatly to the user
            //ask the user if they would like to continue
            //if no break and end file
            // if yes return to data input

    }

}
