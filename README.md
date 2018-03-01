# Standard-Deviation
package com.company;



        import static com.company.ProjConstants.*;

public class StDeviation {

    // ---------*---------*---------*---------*---------*---------*---------*---------*

    private int[] Data = new int[MAXDATA];
    private int counter = 0;
    private double theAverage;
    private double theVariance;
    private double theStDeviation;

    // ---------*---------*---------*---------*---------*---------*---------*---------*

    public void addNewDataItem(int dataItem) {
        if (counter <= MAXDATA){
            Data[counter]= dataItem;
            counter++;
        }

    }// end addNewDataItem

    // ---------*---------*---------*---------*---------*---------*---------*---------*

    public int getNumberOfDataItems()
    {
        return counter;
    }//end getNumberOfDataItems

    // ---------*---------*---------*---------*---------*---------*---------*---------*

    public double calcAverage() {
        double total = 0;

        for (int i = 0; i < counter; i++) {
            total += Data[i];
        }theAverage = total / counter;

        return theAverage;

    }// end calcAverage

    // ---------*---------*---------*---------*---------*---------*---------*---------*

    public double calcVariance() {
        double total = 0;

        for (int i = 0; i < counter; i++) {
            total += Math.pow(Data[i] - theAverage,2);
        }// end for

     theVariance = total / counter;
        return theVariance;

    }// end calcVariance

    // ---------*---------*---------*---------*---------*---------*---------*---------*

    public double calcStandardDeviation() {
        return Math.sqrt(theVariance);
    }// end calcStandardDeviation

    // ---------*---------*---------*---------*---------*---------*---------*---------*


}// end public class StDeviation
