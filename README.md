# Standard-Deviation
package com.company;

import static com.company.ProjConstants.*;


public class StDeviation {

    // ---------*---------*---------*---------*---------*---------*---------*---------*
    // As discussed in class we are using a class populated with Project Constants to
    // ensure help manage the project data. This ensures that each class can access the
    // constant values, but in the event that a change is needed/required that this will
    // only need to be made in one location, or file.
    //
    // Notice: If I had not done the "static import com.company.ProjConstants.*;" then
    //         the use of the constant would have been written as:
    //
    //         private int[] Data = new int[ProjConstants.MAXDATA];
    //
    private int[] Data = new int[MAXDATA];
    private int currSize = 0;

    // ---------*---------*---------*---------*---------*---------*---------*---------*
    // The following method will take a new data item and add it into the 1 Dimensional
    // Array of data values to be used later.
    //
    // You MUST write this method and I will use it during testing
    //
    public void addNewDataItem(double dataItem) {
        if (currSize >= MAXDATA) return;

        int newData = (int) dataItem;
        Data[getNumberOfDataItems()] = newData;
        currSize++;

    }

    // ---------*---------*---------*---------*---------*---------*---------*---------*
    // The following method will return the total number of data items currently stored
    //
    // You MUST write this method and I will use it during testing
    //
    public int getNumberOfDataItems() {
        return currSize;
    }

    // ---------*---------*---------*---------*---------*---------*---------*---------*
    // The following method returns a double precision value which is the average of all
    // of the data values
    //
    // You MUST write this method and I will use it during testing
    //
    public double calcAverage() {
        double total = 0;
        double theAverage = 0;

        for (int i = 0; i < currSize; i++) {
            total += Data[i];
        }
        theAverage = total / currSize;
        return theAverage;
    }

    // ---------*---------*---------*---------*---------*---------*---------*---------*
    // The following method returns a double precision value which is the Variance of all
    // of the data values
    //
    // You MUST write this method and I will use it during testing
    //
    public double calcVariance() {
        double theAverage = calcAverage();
        double total = 0;
        double theVariance= 0;
        for (int i = 0; i < currSize; i++) {
            total += Math.pow(Data[i] - theAverage, 2);
        }
        theVariance = total / currSize;

        return theVariance;
    }


    // ---------*---------*---------*---------*---------*---------*---------*---------*
    // The following method returns a double precision value which is the Standard
    // Deviation of all of the data values
    //
    // You MUST write this method and I will use it during testing
    //
    public double calcStandardDeviation() {

        double theStDeviation = Math.pow(calcVariance(), 2);
        return theStDeviation;
    }
}
