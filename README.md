# Tech Interview 

2. 
````
function checkInput() {
    var email = document.forms["login"]["email"].value;   
    var password = document.forms["login"]["password"].value;
    var mock=  /^(?=.*[0-9])/;

    if (email == "" || password == "") {
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

3. 


