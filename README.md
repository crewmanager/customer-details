# customer-details
``index.html``

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width" />
    <title>hello</title>
    <base href="/" />
    <link rel="icon" href="favicon.ico" />
    <link type="text/css" rel="stylesheet" href="main.css" />
  </head>
  <body>
    <main>
      <div class="container">
        <div class="text">
           Contact Details
        </div>
        <form action="#">
           <div class="form-row">
              <div class="input-data">
                 <input id="fname" type="text" required>
                 <div class="underline"></div>
                 <label for="">First Name</label>
              </div>
              <div class="input-data">
                 <input id="lname" type="text" required>
                 <div class="underline"></div>
                 <label for="">Last Name</label>
              </div>
           </div>
           <div class="form-row">
              <div class="input-data">
                 <input id="ename" type="text" required>
                 <div class="underline"></div>
                 <label for="">Email Address</label>
              </div>
              <div class="input-data">
                 <input id="pname" type="text" required>
                 <div class="underline"></div>
                 <label for="">Phone Number</label>
              </div>
           </div>
           <div class="form-row">
           <div class="input-data textarea">
              <textarea id="wname" rows="8" cols="80" required></textarea>
              <br />
              <div class="underline"></div>
              <label for="">Write your message</label>
              <br />
              <div class="form-row submit-btn">
                 <div class="input-data">
                    <div class="inner"></div>
                    <input type="submit" value="submit">
                 </div>
              </div>
        
        <!-- <button type="submit">Click Me!</button> -->
      </form>
    </div>
      <section id="greeting"></section>
    </main>
  </body>
</html>
```

``main.css``

```

@import url('https://fonts.googleapis.com/css?family=Poppins:400,500,600,700&display=swap');
*{
  margin: 0;
  padding: 0;
  outline: none;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}
body{
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  padding: 10px;
  font-family: 'Poppins', sans-serif;
  background: linear-gradient(115deg, #56d8e4 10%, #9f01ea 90%);
}
.container{
  max-width: 800px;
  background: #fff;
  width: 800px;
  padding: 25px 40px 10px 40px;
  box-shadow: 0px 0px 10px rgba(0,0,0,0.1);
}
.container .text{
  text-align: center;
  font-size: 41px;
  font-weight: 600;
  font-family: 'Poppins', sans-serif;
  background: -webkit-linear-gradient(right, #56d8e4, #9f01ea, #56d8e4, #9f01ea);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.container form{
  padding: 30px 0 0 0;
}
.container form .form-row{
  display: flex;
  margin: 32px 0;
}
form .form-row .input-data{
  width: 100%;
  height: 40px;
  margin: 0 20px;
  position: relative;
}
form .form-row .textarea{
  height: 70px;
}
.input-data input,
.textarea textarea{
  display: block;
  width: 100%;
  height: 100%;
  border: none;
  font-size: 17px;
  border-bottom: 2px solid rgba(0,0,0, 0.12);
}
.input-data input:focus ~ label, .textarea textarea:focus ~ label,
.input-data input:valid ~ label, .textarea textarea:valid ~ label{
  transform: translateY(-20px);
  font-size: 14px;
  color: #3498db;
}
.textarea textarea{
  resize: none;
  padding-top: 10px;
}
.input-data label{
  position: absolute;
  pointer-events: none;
  bottom: 10px;
  font-size: 16px;
  transition: all 0.3s ease;
}
.textarea label{
  width: 100%;
  bottom: 40px;
  background: #fff;
}
.input-data .underline{
  position: absolute;
  bottom: 0;
  height: 2px;
  width: 100%;
}
.input-data .underline:before{
  position: absolute;
  content: "";
  height: 2px;
  width: 100%;
  background: #3498db;
  transform: scaleX(0);
  transform-origin: center;
  transition: transform 0.3s ease;
}
.input-data input:focus ~ .underline:before,
.input-data input:valid ~ .underline:before,
.textarea textarea:focus ~ .underline:before,
.textarea textarea:valid ~ .underline:before{
  transform: scale(1);
}
.submit-btn .input-data{
  overflow: hidden;
  height: 45px!important;
  width: 25%!important;
}
.submit-btn .input-data .inner{
  height: 100%;
  width: 300%;
  position: absolute;
  left: -100%;
  background: -webkit-linear-gradient(right, #56d8e4, #9f01ea, #56d8e4, #9f01ea);
  transition: all 0.4s;
}
.submit-btn .input-data:hover .inner{
  left: 0;
}
.submit-btn .input-data input{
  background: none;
  border: none;
  color: #fff;
  font-size: 17px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 1px;
  cursor: pointer;
  position: relative;
  z-index: 2;
}
@media (max-width: 700px) {
  .container .text{
    font-size: 30px;
  }
  .container form{
    padding: 10px 0 0 0;
  }
  .container form .form-row{
    display: block;
  }
  form .form-row .input-data{
    margin: 35px 0!important;
  }
  .submit-btn .input-data{
    width: 40%!important;
  }
}

button[type="submit"] {
    padding: 5px 20px;
    margin: 10px auto;
    float: right;
}

#greeting {
    margin: 10px auto;
    padding: 10px 60px;
    border: 1px solid #222;
}

#greeting:empty {
    display: none;
}
```

``main.mo``
```
import Error "mo:base/Error";
import Text "mo:base/Text";
import HashMap "mo:base/HashMap";

actor {

  stable var state = 0;
  type Details ={
    firstname : Text;
    lastname : Text;
    email : Text;
    phone : Nat;
    message : Text;
  };
  var map = HashMap.HashMap<Text,Details>(0,Text.equal,Text.hash);
  public func insert(customerName : Text,info: Details) : async Text {
    let details: Details={
      firstname = info.firstname;
      lastname = info.lastname;
      email = info.email;
      phone = info.phone;
      message = info.message;
    };
    map.put(customerName,details);
    return "Data Inserted Successfully"
  };
  public func fetchData(customerName:Text) :async Details {
    let data: Details = switch(map.get(customerName)){
      case(?value){value};
      case(null) {throw Error.reject("Key does not exist")};
    };
    return data;
  }
};
```


``index.js``

```
import { hello_backend } from "../../declarations/hello_backend";

document.querySelector("form").addEventListener("submit", async (e) => {
  e.preventDefault();
  const button = e.target.querySelector("button");

  const firstname = document.getElementById("fname").value.toString();
  const lastname = document.getElementById("lname").value.toString();
  const email = document.getElementById("ename").value.toString();
  const phone = document.getElementById("pname").value.toString();
  const message = document.getElementById("wname").value.toString();

  button.setAttribute("disabled", true);

  // Interact with foo actor, calling the greet method
  const greeting = await hello_backend.greet(firstname,lastname,email,phone,message);

  button.removeAttribute("disabled");

  document.getElementById("greeting").innerText = greeting;

  return false;
});
```
