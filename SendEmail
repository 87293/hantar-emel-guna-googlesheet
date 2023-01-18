
function sendEmail(){



var ss = SpreadsheetApp.openById("LIST EMEL - GOOGLE SHEET ID/NOMBOR DALAM LINK BROWSER TAB");
var sheet = ss.getSheetByName("NAMA SHEET DLM GOOGLE SHEET/TAB");
var json_data = getData(sheet);

function getData(sheet){
   var jo = {};
   var dataArray = [];
// collecting data from 2nd Row , 1st column to last row and last    // column sheet.getLastRow()-1
var rows = sheet.getRange(2,1,sheet.getLastRow()-1, sheet.getLastColumn()).getValues();
for(var i = 0, l= rows.length; i<l ; i++){
     var dataRow = rows[i];
     var record = {};
      record['email'] = dataRow[0];
     Logger.log(dataRow + " is email");
      dataArray.push(record);
   }
   jo = dataArray;
   var result = JSON.stringify(jo);
return jo;
}


for(var j=0;j<json_data.length;j++) {

//var message=

  var cal = CalendarApp.getOwnedCalendarById("GOOGLE CALENDAR ID");

  /* Get all events for today */
  var events = cal.getEventsForDay(new Date());

if (events.length > 0) {
    var body = 'Daily Notice' + "\n\n";
    var tz = Session.getScriptTimeZone();

    /* Concatenate the events list */
    for (var i = 0; i < events.length; i++) {
      body += Utilities.formatDate(events[i].getStartTime(), tz, 'dd/MM ') + '-';
      body += Utilities.formatDate(events[i].getEndTime(), tz, 'dd/MM/YYYY') + ' :  ';
      body += events[i].getTitle() + "\n";
    }

    /* Send email digest */
  //  MailApp.sendEmail(mailto, 'Google Calender - Summary', body);

  }


MailApp.sendEmail({to: json_data[j].email, cc: 'aminuddin.adnan@igbis.edu.my', subject: "Google Calender - Summary", body, noReply:true} );
}

}
