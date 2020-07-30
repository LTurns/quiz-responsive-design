# Tech Quiz 


1. 

Please refer <a href="http://lizzie-mockup-tech.s3-website.us-east-2.amazonaws.com">here </a> for my mock-up. I was able to add the images and text very easily. If that was not the case, I would have added a div labelled "image" and Lorem Ipsum as filler. 

To see code, please visit [CSS](https://github.com/LTurns/responsive_design/blob/master/stylesheet.css) and [HTML](https://github.com/LTurns/responsive_design/blob/master/index.html) files in repo.

2. 
````
function checkInput() {
    var email = document.forms["login"]["email"].value;   //grabbing value within HTML form
    var password = document.forms["login"]["password"].value;
    var mock=  /^(?=.*[0-9])/;   //brief use of regex for special characters 

    if (email == "" || password == "") {     //conditionals 
        alert("Both boxes must be filled out") 
        return false;
    } else  if ( !email.includes("@")) {
        alert("email not recognised");
        return false;
    } else if (password.length < 6 ){
        alert("password too short")
        return false;
    } else if(!password.match(mock)){
        alert("password must contain at least 1 number")
        return false;
    } 
}  

````

Data Qs.

````
var records = [
  { user_id: 1, device: "Windows 10", action: "start", date_actioned: 100 },
  { user_id: 2, device: "OSX 15.4", action: "start", date_actioned: 200 },
  { user_id: 1, device: "iPhone 8s", action: "start", date_actioned: 250 },
  { user_id: 1, device: "Windows 10", action: "stop", date_actioned: 370 },
  { user_id: 1, device: "iPhone 8s", action: "stop", date_actioned: 410 },
  { user_id: 2, device: "OSX 15.4", action: "stop", date_actioned: 490 },
  { user_id: 3, device: "Android 9.1", action: "start", date_actioned: 700 },
];

````


3. 

````

function getUsers(records, action, start_time, end_time) {
  var data = []; // empty array used to store and separate data

  for (var i = 0; i < records.length; i++) {
    //iterating over records array
    var obj = records[i]; // defining 'obj' as individual objects within records
    if (
      obj.action === action &&   //conditionals
      obj.date_actioned >= start_time &&
      obj.date_actioned <= end_time
    ) {
      data.push(obj.user_id); //push the user_id of any qualifying objects to data array
    }
  }
  return data;
}

this.getUsers(records, "start", 700, 900); //activates function

````

4. 

````

function getPlaybackTime(user_id, records){

    var start = [] //arrays to separate start/stop data
    var stop = []
   
       for(var i = 0; i < records.length; i++) {  //iteration
         var obj = records[i];
           if (obj.user_id === user_id && obj.action == "start") {
           start.push(obj.date_actioned);
           }
           if (obj.user_id === user_id && obj.action == "stop"){
             stop.push(obj.date_actioned);
           }
       } 
       if (stop.length !== 0){
         return (stop[stop.length-1] - start[0]); //calculates playback time by getting first and last result
       } else { return "device still playing"}  //alternative if device not yet stopped
        
   }
   
   this.getPlaybackTime(1, records) //activates function

   ````

5. Inline comments added above. 

6. Shortcomings & Limitations

* Refactoring - lots of code here. With more time, I would attempt to make some of the steps much clearer and cleaner. 
* Scalability may be a potential limitation - if there were 1000s of results, pushing every "start" and "stop" into a
separate array would take a lot of time. One way to cater against this would be to focus on sections of the array instead of iterating over every object - we know that the initial start times are likely to be at the beginning of the array, for example. 




