# BirthDayCalculatorJava
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Calendar;
import java.util.Date;
import java.util.TimeZone;
public class Duration {

	
		public static void main(String arg[])
		{
			/*BirthDay Date annd Time*/
			String BirthDayDate = "08-Feb-1992";
			String BirthDaytime = "11:35:01 AM";
					
		
			SimpleDateFormat simpleDateTimeFormat = new SimpleDateFormat("dd-MMM-yyyy hh:mm:ss a");
	
		      try {
		    	  /**Get Current Time in Millisecond*/
		    	long currentTime = System.currentTimeMillis();
		        Date date1 = simpleDateTimeFormat.parse(BirthDayDate +" "+BirthDaytime );
		        String currentTimeString = simpleDateTimeFormat.format(currentTime);
		        Date date2 = simpleDateTimeFormat.parse(currentTimeString);//.parse(d2 +" "+time2);
		          
		        printDifference(date1,date2);

		      } catch (ParseException e) {
		        e.printStackTrace();
		      }

		    }

		    public static void printDifference(Date startDate, Date endDate){

		        //Difference in milliseconds
		        long different = endDate.getTime() - startDate.getTime();

		        long secondsInMilli = 1000;
		        long minutesInMilli = secondsInMilli * 60;
		        long hoursInMilli = minutesInMilli * 60;
		        long daysInMilli = hoursInMilli * 24;
		        
		        
		        long elapsedDays = different / daysInMilli;
		        different = different % daysInMilli;

		        long elapsedHours = different / hoursInMilli;
		        different = different % hoursInMilli;

		        long elapsedMinutes = different / minutesInMilli;
		        different = different % minutesInMilli;

		        long elapsedSeconds = different / secondsInMilli;

		        int ago = 0 ;
		        System.out.printf("Abous ");
		        if(elapsedDays !=0)
		        {
		        	if(elapsedDays>365)
		        	{
		        		System.out.printf(
			  		            "%d years ",(int) elapsedDays/365);
		        	}else if(elapsedDays >30){
		        		System.out.printf(
			  		            "%d years ",(int) elapsedDays/30);
		        	}else
		        	{	
		        	System.out.printf(
		  		            "%d days ", elapsedDays);
		        	}
		        	  ago = 1;
		        }
		        if(elapsedHours != 0)
		        {
		        	  System.out.printf(
		  		            "%d hours ",elapsedHours);
		        	  ago = 1;
		        }
		        if(elapsedMinutes != 0)
		        {
		        	  System.out.printf(
		  		            "%d minutes ", elapsedMinutes);
		        	  ago = 1;
		        }
		        if(elapsedSeconds != 0)
		        {
		        	  System.out.printf(
			  		            "%d seconds ", elapsedSeconds);
			        	  ago = 1;
		        }
		        if( ago ==1)
		        {
		        System.out.printf(
	  		            "ago\n");
		        }   
		        else
		        {
		            System.out.printf(
		  		            "0 sec ");
		        }

		    }
	}


