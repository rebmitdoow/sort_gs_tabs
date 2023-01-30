function TabSorting() {
  var ss = SpreadsheetApp.getActiveSpreadsheet();
  var sheets = ss.getSheets();
  var sheetNameArray = [];
  var active = ss.getActiveRange();

  for (var i = 0; i < sheets.length; i++) {
      sheetNameArray.push(sheets[i].getName());
  }
//To avoid sorting problems when having numbers like 1 and 11, use the "collator" function
  var collator = new Intl.Collator(undefined, {numeric: true, sensitivity: 'base'});
  sheetNameArray.sort(collator.compare);


  for( var j = 0; j < sheets.length; j++ ) {
    ss.setActiveSheet(ss.getSheetByName(sheetNameArray[j]));
    ss.moveActiveSheet(j + 1);
  }
//If you want to add exceptions and place specific tabs first, replace "tab name ..." with the names of your specific tabs 
["tab name 1", "tab name 2"].forEach((name,i)=>{
  ss.setActiveSheet(ss.getSheetByName(name));
  ss.moveActiveSheet(i + 1);                                                                       
  })

active.activate();

}
