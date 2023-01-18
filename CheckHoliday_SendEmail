//semak hari ini tarikh ape? 
//checkdate() tu untuk dapatkan tarikh hari ini, tarikh semasa
//Logger.log(checkDate + " is holiday"); ----- untuk dapatkan nilai "tarikh"/ "date" 

function myFunction() { sendEmail();
  var checkDate = new Date(); 
  if( holiday(checkDate) == 1){
    Logger.log(checkDate + " is holiday");
    return
  }
  else{
    
    Logger.log(checkDate + " is not holiday");
    sendEmail();


    


  }
}

function holiday(dateToCheck) {
  
  
  //var cal = CalendarApp.getCalendarById("letak calendar ID di sini");
  //var cal = CalendarApp.getCalendarsByName("yang ini pakai nama kalendar");
  //dua-dua boleh pakai, guna ID atau Nama
  var cal = CalendarApp.getCalendarsByName("NAMA CALENDAR");

// exclusion list of holidays which are not part of MOM published public holiday
  const nonHolidayArray = ["Christmas Eve","New Year's Eve","Children's Day","Easter Saturday","Easter Sunday"];
  //var holidays = cal.getEventsForDay(dateToCheck);
  var holidays = cal[0].getEventsForDay(dateToCheck);
  
  var isHoliday = 0;
  // if there is only one holiday per day  
  if (holidays.length >= 1){
    for (var i = 0; i < holidays.length; i++){
      var eventTitle = holidays[i].getTitle();
      // if the title is not in the exclusion list, then is holiday 
      if ( nonHolidayArray.indexOf(eventTitle) == -1 ){
        isHoliday = 1;
      }
    }
  }
  return isHoliday;
}
