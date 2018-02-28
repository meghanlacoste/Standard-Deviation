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

        StDeviation calcSDev =  new StDeviation();

                String userFileName;

                System.out.println("");
                System.out.println("Please type in the file name\n");

        Scanner scanSystemIn = new Scanner(System.in);

        userFileName = scanSystemIn.next();

        File userFile = new File("tempfilenums.txt");
        Scanner scanUserFile = new Scanner("tempfilenums.txt");

    // Display the user input now stored in "userInput"
    System.out.println("\nThe user input: " + userFileName);

    try {

        while (filedone == false){
            //for(int counter =0; counter < MAXDATA; counter++) {


            if (scanUserFile.hasNext()) {
                counter = scanUserFile.nextInt();
                System.out.print(" - " + counter);

                calcSDev.addNewDataItem(counter);


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
                fileDone = true;
                //break;
            }// end else
        }
    }
    catch (FileNotFoundException e) {

        System.out.println("------------------------------------------------");

        System.out.println(e);
        e.printStackTrace();
    }


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
