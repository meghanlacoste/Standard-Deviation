# Standard-Deviation
package com.company;

// ---------*---------*---------*---------*---------*
// The use of static imports is something that should be used carefully.
// I have only ever used this technique for the project wide constants.
//
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

import static com.company.ProjConstants.*;

public class Main {

    public static void main(String[] args) {

        boolean fileDone = false;
        boolean proceed = true;
        double theAverage = 0;
        double theVariance = 0;
        double theStDeviation = 0;
        int counter = 0;
        String userFileName;
        String userInput;

        StDeviation calcSDev =  new StDeviation();

        while (proceed= true) {
            try {

                System.out.println("");
                System.out.println("Please type in the file name\n");

                Scanner scanSystemIn = new Scanner(System.in);
                userFileName = scanSystemIn.next();

                File userFile = new File(userFileName);
                Scanner scanUserFile = new Scanner(userFile);

                System.out.println("\nThe user input: " + userFileName);

                while (!fileDone) {

                    if (scanUserFile.hasNext()) {
                        counter = scanUserFile.nextInt();
                        System.out.print(" -- " + counter);

                        calcSDev.addNewDataItem(counter);
                        if (counter > MAXDATA) {
                            System.out.printf("The file chosen is too large; the file was not completely read into array");
                        }// end if (counter>= MAXDATA)
                    }// end (scanUserFile.hasNext())
                    else {
                        System.out.println();
                        // System.out.println("==================================================================\n");
                        System.out.print("\n\n The file has been completely read");
                        scanUserFile.close();
                        System.out.println();
                        fileDone = true;
                    }// end else
                }// end while

            } catch (FileNotFoundException e) {

                System.out.println("------------------------------------------------");

                System.out.println(e);
                e.printStackTrace();
            }

            theAverage = calcSDev.calcAverage();

            theVariance = calcSDev.calcVariance();

            theStDeviation = calcSDev.calcStandardDeviation();

            //  the range of values that contain 68% of the observations, 95% of the observations, and 99% of the observations.
            double theRange68 = (theAverage + theStDeviation) - (theAverage - theStDeviation);
            double theRange95 = (theAverage + 2 * theStDeviation) - (theAverage - 2 * theStDeviation);
            double theRange99 = (theAverage + 3 * theStDeviation) - (theAverage - 3 * theStDeviation);

            // if counter> MaxData, print "The file chosen is too large; file not completely read into array"
// print within 4 decimal point
            System.out.println("------------------------------------------------");
            System.out.printf("For the values found in file:");
            System.out.println(" ");
            System.out.printf("The Average is: " + theAverage);
            System.out.println(" ");
            System.out.printf("The Variance is: " + theVariance);
            System.out.println(" ");
            System.out.printf("The Standard Deviation is: " + theStDeviation);
            System.out.println(" ");
            System.out.println("==================================================================\n");
            System.out.print("The lower bound: "+ (theAverage - theStDeviation));
            System.out.print("             The average: " + theAverage);
            System.out.print("             The uppper bound: "+ (theAverage + theStDeviation));

            System.out.println("The Range of the values within 68% of the observations is: " + theRange68);
            System.out.println("The Range of the values within 95% of the observations is: " + theRange95);
            System.out.println("The Range of the values within 99% of the observations is: " + theRange99);
            System.out.println();
            System.out.println("==================================================================\n");
            System.out.println();


            System.out.println("");
            System.out.println("Would you like to continue? Press 'Y' if yes and 'N' if you are done\n");

            Scanner scanSystemIn = new Scanner (System.in);
            userInput = scanSystemIn.next();
           // while ( !(s.hasNext("n") || s.hasNext("N")) ){
          //      System.out.println("process is finished");
              //  proceed = false;
         //   }

        }// while proceed= true

      //  if(userInput = String) {
     //       proceed = true

      //  }
      //  else
      //  {
     //       System.out.println("process finished");
        //    fileDone = true;
      //  }





    //- Prompt User for file name
    // -> if the file exists then prepare to read the data using the StDeviation methods
    // ->: read the data from the file in a loop
    //  ** add data item into data set using Standard Deviation Method to add data

    //  ->: if the data file was not read completely then display warning to user and continue

    //display all information neatly to the user
    //ask the user if they would like to continue
    //if no break and end file
    // if yes return to data input

        System.out.println("------------------------------------------------");

}// end main method
}// end main class
