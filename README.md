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
        double theAverage = 0;
        double theVariance = 0;
        double theStDeviation = 0;
        int counter = 0;

        StDeviation calcSDev =  new StDeviation();

                String userFileName;

                System.out.println("");
                System.out.println("Please type in the file name\n");

                Scanner scanSystemIn = new Scanner(System.in);

                      userFileName = scanSystemIn.next();

        File userFile = new File("tempfilenums.txt");

        Scanner scanUserFile = new Scanner("tempfilenums.txt");

          System.out.println("\nThe user input: " + userFileName);


        try {


             while (fileDone == false){
                //for(int counter =0; counter < MAXDATA; counter++) {


                      if (scanUserFile.hasNext()) {
                         counter = scanUserFile.nextInt();
                         System.out.print(" - " + counter);

                          calcSDev.addNewDataItem(counter);
                      }// end if


                            else {
                                 System.out.println("==================================================================\n");
                                 System.out.print("\n\nDataFileFILE has been completely READ");
                                 scanUserFile.close();
                                 System.out.println("==================================================================\n");
                                 fileDone = true;
                            }// end else
               }// end while

            }
        catch (FileNotFoundException e) {

            System.out.println("------------------------------------------------");

             System.out.println(e);
             e.printStackTrace();
        }


        theAverage = calcSDev.calcAverage();

        theVariance = calcSDev.calcVariance();

        theStDeviation = calcSDev.calcStandardDeviation();

        //  the range of values that contain 68% of the observations, 95% of the observations, and 99% of the observations.
        double theRange68 = 2*(theAverage - theStDeviation);
        double theRange95 = 2*(theAverage-2*theStDeviation);
        double theRange99 = 2*(theAverage-3*theStDeviation);






        System.out.println("==================================================================\n");
        System.out.printf("The Average is: " + theAverage);
        System.out.printf("The Variance is: " + theVariance);
        System.out.printf("The Standard Deviation is: " + theStDeviation);
        System.out.println("==================================================================\n");

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

}// end main method
}// end main class
