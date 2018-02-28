# Standard-Deviation
com.company;

// ---------*---------*---------*---------*
// The use of static imports is something that should be used carefully.
// I have only ever used this technique for the project wide constants.
//
        import static com.company.ProjConstants.*;

public class StDeviation {

    // ---------*---------*---------*---------*---------*---------*---------*---------*

    private int[] Data = new int[MAXDATA];
    private int counter = 0;
    private double theAverage;
    private double theVariance;
    private double theStDeviation;

    // ---------*---------*---------*---------*---------*---------*---------*---------*
// The following method will take a new data item and add it into the 1 Dimensional
// Array of data values to be used later.
//
// You MUST write this method and I will use it during testing
//
    public void addNewDataItem(int dataItem) {
        if (counter <= MAXDATA){
            Data[counter]= dataItem;
            // int newData = (int) dataItem;
            //  Data[getNumberOfDataItems()] = newData;
            counter++;
        }

    }// end addNewDataItem

    // ---------*---------*---------*---------*---------*---------*---------*---------*
// The following method will return the total number of data items currently stored
//
// You MUST write this method and I will use it during testing
//
    public int getNumberOfDataItems() {
        return counter;
    }//end getNumberOfDataItems

    // ---------*---------*---------*---------*---------*---------*---------*---------*
// The following method returns a double precision value which is the average of all
// of the data values
//
// You MUST write this method and I will use it during testing
//
    public double calcAverage() {
        double total = 0;
        //double theAverage = 0;

        for (int i = 0; i < counter; i++) {
            total += Data[i];
        }
        theAverage = total / counter;
        return theAverage;
    }
// end calcAverage
    // ---------*---------*---------*---------*---------*---------*---------*---------*
// The following method returns a double precision value which is the Variance of all
// of the data values

    public double calcVariance() {
        //double theAverage = calcAverage();
        double total = 0;
        //double theVariance= 0;
        for (int i = 0; i < counter; i++) {
            total += Math.pow(Data[i] - theAverage,2);
        }
        theVariance = total / counter; //?

        return theVariance;
    }// end calcVariance
    

       public double calcStandardDeviation() {
        return Math.sqrt(theVariance);
        }// end calcStandardDeviation

}// end public class StDeviation


