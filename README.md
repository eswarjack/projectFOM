# projectFOM
<!DOCTYPE html>
<html>
<head>
    <title>Login and Registration Form</title>
    <style>
    *{
    margin: 0;
    padding: 0;
    font-family: sans-serif;
}
.hero{
    height: 100%;
    width: 100%;
    background-image:url(https://images.unsplash.com/photo-1567306295427-94503f8300d7?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&w=1000&q=80);
      background-repeat: no-repeat;
background-size: cover;
    position: absolute;
    background-attachment: fixed;
}
.form-box{
     width: 400px;
    height: 550px;
    margin: 4% auto;
    position: relative;
    background-color:#ffffff;
    padding: 5px;
    overflow: hidden;
    border-style:ridge;
    border-color:#66cc00;
    border-width:8px;
    opacity: 0.6;
  filter: alpha(opacity=200);
}
.button-box{
     width: 220px;
    margin: 37px auto;
    position: relative;
    box-shadow: 0 0 20px 9px #b3ff1a;
    border-radius: 30px;
}
.toggle-btn{
 font-weight: bold;
  color: #000000;
    padding: 10px 30px;
    cursor: pointer;
    background: transparent;
    border: 0;
    outline: none;
    position: relative;
    
}
#btn{
    top: 0;
    left: 0;
    position: absolute;
    width: 110px;
    height: 100%;
    background: linear-gradient(to right,#33cc00,#ffff00);
    border-radius: 30px;
    transition: .5s;
}
.social-icons{
    margin: 30px auto;
    text-align: center;
}
.social-icons img{
    width: 30px ;
    margin: 0 12px;
    box-shadow: 0 0 20px 0 #7f7f7f3d;
    cursor: pointer;
    border-radius: 50%;
}
.input-group{
    font-weight: bold;
  color: #000000;
    top: 180px;
    position: absolute;
    width: 280px;
    transition: .5s;
}
.input-field{
 font-weight: bold;
  color: #000000;
    width: 100%;
    padding: 10px 0;
    margin: 5px 0;
    border-left: 0;
    border-top: 0;
    border-left: 0;
    border-bottom: 1px solid #999;
    outline: none;
    background: transparent;
}
.submit-btn{
 font-weight: bold;
  color: #000000;
    width: 85%;
    padding: 10px 30px;
    cursor: pointer;
    display: block;
    margin: auto;
    background:linear-gradient(to right,#33cc00,#ffff00);
    outline: none;
    border-radius: none;
    
}
.check-box{
    margin: 30px 10px 30px 0;
}
span{
    color: #777;
    font-size: 12px;
    bottom: 68px;
    position: absolute;
}
#login{
    left: 50px;
}
#register{
    left: 450px;
}
.custom-select {
  position: relative;
  font-size:14px;
  width: 100%;
    padding: 10px 0;
    margin: 5px 0;
    border-left: 0;
    border-top: 0;
    border-left: 0;
    outline: none;
    background: transparent;
}

.custom-select select {
  display: none; 
}

.select-selected {
  background-color: white;
}
.select-selected:after {
  position: absolute;
  content: "";
  top: 14px;
  right: 10px;
  width: 0;
  height: 0;
  border: 6px solid transparent;
  border-color: black transparent transparent transparent;
}
.select-selected.select-arrow-active:after {
  border-color: transparent transparent black transparent;
  top: 7px;
}
.select-items div,.select-selected {
  color:grey;
  padding:0;
  border: 1px solid transparent;
  border-color: transparent transparent rgba(0, 0, 0, 0.1) transparent;
  cursor: pointer;
  user-select: none;
}
.select-items {
  position: absolute;
  background-color:white;
  top: 100%;
  left: 0;
  right: 0;
  z-index: 99;
}
.select-hide {
  display: none;
}

.select-items div:hover, .same-as-selected {
  background-color: rgba(0, 0, 0, 0.1);
}
    </style>
</head>
<body>
<div class="hero">
    <div class="form-box">
        <div class="button-box">
            <div id="btn"></div>
            <button type="button" class="toggle-btn" onclick="login()">Log In</button>
            <button type="button" class="toggle-btn" onclick="register()">Register</button>
        </div>
        <div class="social-icons"> 
    </div>
        <form id="login" class="input-group">
        <input type="text" class="input-field" placeholder="User Id/Mobile Number" required>
        <input type="password" class="input-field" placeholder="Enter Password" required>
        <input type="checkbox" class="check-box"><span>Remember Password</span>
        <button type="submit" class="submit-btn">Log In</button>
        </form>
        <form id="register" class="input-group">
        <input type="text" class="input-field" placeholder="User Id" required>
        <input type="text" class="input-field" placeholder="Moblie Number" required>
        <div class="custom-select" style="width:200px;">
  <select>
     <label for="ut"><b>User Type</b></label>
    <option value="0">User Type</option>
    <option value="1">Farmer</option>
    <option value="2">Customer</option>
    <option value="3">Dealer</option>
    
  </select>
</div>

<script>
var x, i, j, selElmnt, a, b, c;
/*look for any elements with the class "custom-select":*/
x = document.getElementsByClassName("custom-select");
for (i = 0; i < x.length; i++) {
  selElmnt = x[i].getElementsByTagName("select")[0];
  /*for each element, create a new DIV that will act as the selected item:*/
  a = document.createElement("DIV");
  a.setAttribute("class", "select-selected");
  a.innerHTML = selElmnt.options[selElmnt.selectedIndex].innerHTML;
  x[i].appendChild(a);
  /*for each element, create a new DIV that will contain the option list:*/
  b = document.createElement("DIV");
  b.setAttribute("class", "select-items select-hide");
  for (j = 1; j < selElmnt.length; j++) {
    /*for each option in the original select element,
    create a new DIV that will act as an option item:*/
    c = document.createElement("DIV");
    c.innerHTML = selElmnt.options[j].innerHTML;
    c.addEventListener("click", function(e) {
        /*when an item is clicked, update the original select box,
        and the selected item:*/
        var y, i, k, s, h;
        s = this.parentNode.parentNode.getElementsByTagName("select")[0];
        h = this.parentNode.previousSibling;
        for (i = 0; i < s.length; i++) {
          if (s.options[i].innerHTML == this.innerHTML) {
            s.selectedIndex = i;
            h.innerHTML = this.innerHTML;
            y = this.parentNode.getElementsByClassName("same-as-selected");
            for (k = 0; k < y.length; k++) {
              y[k].removeAttribute("class");
            }
            this.setAttribute("class", "same-as-selected");
            break;
          }
        }
        h.click();
    });
    b.appendChild(c);
  }
  x[i].appendChild(b);
  a.addEventListener("click", function(e) {
      /*when the select box is clicked, close any other select boxes,
      and open/close the current select box:*/
      e.stopPropagation();
      closeAllSelect(this);
      this.nextSibling.classList.toggle("select-hide");
      this.classList.toggle("select-arrow-active");
    });
}
function closeAllSelect(elmnt) {
  /*a function that will close all select boxes in the document,
  except the current select box:*/
  var x, y, i, arrNo = [];
  x = document.getElementsByClassName("select-items");
  y = document.getElementsByClassName("select-selected");
  for (i = 0; i < y.length; i++) {
    if (elmnt == y[i]) {
      arrNo.push(i)
    } else {
      y[i].classList.remove("select-arrow-active");
    }
  }
  for (i = 0; i < x.length; i++) {
    if (arrNo.indexOf(i)) {
      x[i].classList.add("select-hide");
    }
  }
}
document.addEventListener("click", closeAllSelect);
</script>
        <input type="password" class="input-field" placeholder="Enter Password" required>
        <input type="password" class="input-field" placeholder="Re-Enter Password" required>
        <input type="checkbox" class="check-box"><span>I agree to the terms and conditions</span>
        <button type="submit" class="submit-btn">Register</button>
        </form>
    </div>
    
</div>
    <script>
    var x = document.getElementById("login");
    var y = document.getElementById("register");
    var z = document.getElementById("btn");
    function login(){
            x.style.left = "50px";
            y.style.left = "450px";
            z.style.left = "0";
        }
        function register(){
            x.style.left = "-400px";
            y.style.left = "50px";
            z.style.left = "110px";
        }
    </script>

</body>
</html>
