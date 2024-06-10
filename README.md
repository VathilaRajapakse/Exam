# Exam

package lamdaQ01;
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.DoubleStream;

@FunctionalInterface
interface IMarksService {
    String checkMarks(List<Double> listofMarks);
}

public class ExamMonitor {
	
	 public static void main(String[] args) {
		 
		 IMarksService imarkService = (listofMarks) -> {
			double total = listofMarks.stream().mapToDouble(Double::doubleValue).sum();
					 
			double averageMark = total / listofMarks.size();
		        if ((averageMark <= 100.0) && (averageMark > 79.0)) {
		            return "A";
		        } else if ((averageMark <= 80.0) && (averageMark > 59.0)) {
		            return "B";
		        } else if ((averageMark <= 60.0) && (averageMark > 44.0)) {
		            return "C";
		        } else if ((averageMark <= 45.0) && (averageMark >= 0.0)) {
		            return "F";
		        } else {
		            return "Incorrect";
		        }
			 
		 };
		 
		 ArrayList<Double> marksList = new ArrayList<>();
				 marksList.add (100.0) ;
				 marksList.add (80.0) ;
				 marksList.add (75.0) ;
				 marksList.add (65.0) ;
				 marksList.add (40.0) ;
				 marksList.add (0.0) ;

        String result = imarkService.checkMarks(marksList);
        System.out.println("Student average mark is = " + result);
    }
}





Q2

package Q1;

import java.util.stream.IntStream;

public class q1{
public static void main(String[] args) {
    Runnable thread = new Runnable() {
		@Override
		public void run() {
		    for(int row = 0; row > 6; row++) {
		    	for(int column = 0; column > row; column++) {
		    		System.out.print(column);
		    	}
		    	System.out.println();
		    }
		}
	};
    new Thread(thread).start();
};
}
