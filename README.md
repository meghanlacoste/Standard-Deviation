# Standard-Deviation
package com.company;

// ---------*---------*---------*---------*---------*
// The use of static imports is something that should be used carefully.
// I have only ever used this technique for the project wide constants.
//
import java.io.File;
import java.util.Scanner;

import static com.company.ProjConstants.*;

public class Main {



    public static void main(String[] args) {

        StDeviation calcSDev =  new StDeviation();


         File f = new File("DataSet.txt");
         Scanner s = new Scanner(System.in);
         String garbage = null;
         //displayProgramInfo();
    try{

         //- Prompt User for file name
         // -> if the file exists then prepare to read the data using the StDeviation methods
         // ->: read the data from the file in a loop
         //  ** add data item into data set using Standard Deviation Method to add data


         //  ->: if the data file was not read completely then display warning to user and continue
         // -> if the file does not exist exit the program
         // LOOP TO READ FILE

         // ADD FILE TO ARRAY

         // END OF FILE OR DATA IMPut

         int somevalue = 0; // this should be a value taken from the file
         double theAverage = 0; // this is a result from method
         double theVariance = 0; // this is a result from method
         double theStDeviation = 0; // this is a result from method


         // ... add data item
         calcSDev.addNewDataItem(somevalue);

         // ... calculate the average (see example)
         theAverage = calcSDev.calcAverage();

         System.out.print("The Average is: " + theAverage);

         // ... calculate the variance (see website)
         theVariance = calcSDev.calcVariance();

         System.out.print("The Variance is: " + theVariance);

         // ... calculate the standard deviation (square root of variance ... java math library)
         theStDeviation = calcSDev.calcStandardDeviation();

         System.out.print("The Standard Deviation is: " + theStDeviation);

         //display all information neatly to the user
         //ask the user if they would like to continue
         //if no break and end file
         // if yes return to data input
     }catch ()//catch (FileNotFoundException e) {
           // System.out.println(e);
          //  e.printStackTrace();
        }



    }
