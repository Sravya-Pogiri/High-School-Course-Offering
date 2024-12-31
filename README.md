var gradeList = getColumn("Course offerings 2 ", "Year");
var courseList = getColumn("Course offerings 2 ", "Course");
var trackList = getColumn("Course offerings 2 ", "Track ");
var creditList = getColumn("Course offerings 2 ", " Credit");
var typeList = getColumn("Course offerings 2 ", "Type");
var freshmancourseFiltered = [];
var freshmantrackFiltered = [];
var freshmancreditFiltered = [];
var freshmantypeFiltered = [];
var freshmanuserFiltered = [];
var freshmancreditTotal = [];
var sophmorecourseFiltered = [];
var sophmoretrackFiltered = [];
var sophmorecreditFiltered = [];
var sophmoretypeFiltered = [];
var sophuserFiltered = [];
var juniorcourseFiltered = [];
var juniortrackFiltered = [];
var juniorcreditFiltered = [];
var juniortypeFiltered = [];
var junuserFiltered = [];
var seniorcourseFiltered = [];
var seniortrackFiltered = [];
var seniorcreditFiltered = [];
var seniortypeFiltered = [];
var senuserFiltered = [];

for (var i = 0; i < gradeList.length-1; i++) {
  if (gradeList[i] == "FRESHMAN") {
    appendItem(freshmancourseFiltered, courseList[i]);
    appendItem(freshmantrackFiltered, trackList[i]);
    appendItem(freshmancreditFiltered, creditList[i]);
    appendItem(freshmantypeFiltered, typeList[i]);
  }
}
for (var i = 0; i < gradeList.length-1; i++) {
  if (gradeList[i] == "SOPHOMORE") {
    appendItem(sophmorecourseFiltered, courseList[i]);
    appendItem(sophmoretrackFiltered, trackList[i]);
    appendItem(sophmorecreditFiltered, creditList[i]);
    appendItem(sophmoretypeFiltered, typeList[i]);
  }
}
for (var i = 0; i < gradeList.length-1; i++) {
  if (gradeList[i] == "JUNIOR") {
    appendItem(juniorcourseFiltered, courseList[i]);
    appendItem(juniortrackFiltered, trackList[i]);
    appendItem(juniorcreditFiltered, creditList[i]);
    appendItem(juniortypeFiltered, typeList[i]);
  }
}
for (var i = 0; i < gradeList.length-1; i++) {
  if (gradeList[i] == "SENIOR") {
    appendItem(seniorcourseFiltered, courseList[i]);
    appendItem(seniortrackFiltered, trackList[i]);
    appendItem(seniorcreditFiltered, creditList[i]);
    appendItem(seniortypeFiltered, typeList[i]);
  }
}
onEvent("freshmanbutton", "click", function( ) {
  setScreen("Freshman");
});
onEvent("sophmorebutton", "click", function( ) {
  setScreen("Sophmore");
});
onEvent("juniorbutton", "click", function( ) {
  setScreen("Junior");
});
onEvent("seniorbutton", "click", function( ) {
  setScreen("seniorscreen");
});
onEvent("freshmanCourseDropdown", "change", function( ) {
  var course = getText("freshmanCourseDropdown");
  for (var i = 0; i < freshmancourseFiltered.length; i++) {
    if (course == freshmancourseFiltered[i]) {
      setProperty("freshcredit", "text", "Credit: " + freshmancreditFiltered[i]);
      setProperty("freshtrack", "text", "Track: " + freshmantrackFiltered[i]);
    }
  }
});

onEvent("selectFresh", "click", function( ) {
  appendItem(freshmanuserFiltered, getText("freshmanCourseDropdown"));
  var freshtotalv = 0;
  setProperty("freshmanCourses", "text", freshmanuserFiltered + "\n");
  
  i = 0;
  while (freshmancourseFiltered[i] != getText("freshmanCourseDropdown")) {
    appendItem(freshmancreditTotal, freshmancreditFiltered[i]);
    freshtotalv = freshtotalv + freshmancreditTotal[i];
    i++;
  }
  setProperty("freshtotal", "text", "Total credit:" + freshtotalv);
  
});
onEvent("sophcourses", "change", function( ) {
  var course = getText("sophcourses");
  for (var i = 0; i < sophmorecourseFiltered.length; i++) {
    if (course == sophmorecourseFiltered[i]) {
      setProperty("creditSoph", "text", "Credit: " + sophmorecreditFiltered[i]);
      setProperty("TrackSoph", "text", "Track: " + sophmoretrackFiltered[i]);
    }
  }
});
onEvent("selectsoph", "click", function( ) {
  var course = getText("sophcourses");
  appendItem(sophuserFiltered, course);
  setProperty("sophOutput", "text", sophuserFiltered + "\n");
});

onEvent("juniorCourses", "change", function( ) {
  var course = getText("juniorCourses");
  for (var i = 0; i < juniorcourseFiltered.length; i++) {
    if (course == juniorcourseFiltered[i]) {
      setProperty("Creditjun", "text", "Credit: " + juniorcreditFiltered[i]);
      setProperty("Trackjun", "text", "Track: " + juniortrackFiltered[i]);
    }
  }
});
onEvent("selectjun", "click", function( ) {
  var course = getText("juniorCourses");
  appendItem(junuserFiltered, course);
  setProperty("coursesjun", "text", junuserFiltered + "\n");
});

onEvent("selectsen", "click", function( ) {
  var course = getText("seniorCourses");
  appendItem(senuserFiltered, course);
  setProperty("senoutput", "text", senuserFiltered + "\n");
});
onEvent("seniorCourses", "change", function( ) {
  var course = getText("seniorCourses");
  for (var i = 0; i < seniorcourseFiltered.length; i++) {
    if (course == seniorcourseFiltered[i]) {
      setProperty("creditssen", "text", "Credit: " + seniorcreditFiltered[i]);
      setProperty("trackSen", "text", "Track: " + seniortrackFiltered[i]);
    }
  }
});
onEvent("homefresh", "click", function( ) {
  setScreen("HomeScreen");
});
onEvent("homejun", "click", function( ) {
  setScreen("HomeScreen");
});
onEvent("homesen", "click", function( ) {
  setScreen("HomeScreen");
});
onEvent("homesoph", "click", function( ) {
  setScreen("HomeScreen");
});