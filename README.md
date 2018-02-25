# Standard-Deviation
package com.company;

import static com.company.ProjConstants.*;


public class Main { 
 public static void main(String[] args) {
            int Data = 0; // this should be a value taken from the file
        double theAverage = 0; // this is a result from method
        double theVariance = 0; // this is a result from method
        double theStDeviation = 0; // this is a result from method

            StDeviation calcSDev =  new StDeviation();

            // ... add data item
            calcSDev.addNewDataItem(Data);

            // ... calculate the average (see example)
            theAverage = calcSDev.calcAverage();

            System.out.print(theAverage + " ");

            // ... calculate the variance (see website)
            theVariance = calcSDev.calcVariance();

            System.out.print(theVariance+ " ");

            // ... calculate the standard deviation (square root of variance ... java math library)
            theStDeviation = calcSDev.calcStandardDeviation();

             System.out.print(theStDeviation + " ");


        }
}

