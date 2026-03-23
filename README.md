# SARKARI-RESULT-ANOOP
JOBS UPDATE
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SARKARI RESULT ANOOP</title>
<style>
body {font-family: Arial; margin:0; background:#f1f1f1;}
.topbar {background:#ab183d; color:white; text-align:center; padding:15px; font-size:28px; font-weight:bold;}
.subbar {background:#000; color:white; text-align:center; padding:5px;}
.nav {background:#fff; display:flex; flex-wrap:wrap; justify-content:center;}
.nav a {padding:10px 15px; text-decoration:none; color:#000; font-weight:bold; border:1px solid #ddd;}
.container {width:90%; margin:auto; margin-top:15px;}
.grid {display:grid; grid-template-columns:repeat(auto-fit,minmax(300px,1fr)); gap:10px;}
.box {background:#fff; border:2px solid #ab183d;}
.box h3 {margin:0; background:#ab183d; color:#fff; padding:8px; font-size:18px;}
.box ul {list-style:none; padding:10px; margin:0;}
.box ul li {padding:5px 0; border-bottom:1px solid #ddd;}
.admin {position:fixed; bottom:10px; right:10px; background:black; color:white; padding:10px; cursor:pointer;}
#adminPanel {display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:white; padding:20px; overflow:auto;}
input, select {padding:8px; margin:5px; width:200px;}
button {padding:8px 12px; cursor:pointer;}
</style>
</head>
<body>

<div class="topbar">SARKARI RESULT ANOOP</div>
<div class="subbar">WWW.SARKARIRESULTANOOP.COM</div>

<div class="nav">
<a href="#">Home</a>
<a href="#">Latest Jobs</a>
<a href="#">Results</a>
<a href="#">Admit Card</a>
<a href="#">Answer Key</a>
<a href="#">Syllabus</a>
</div>

<div class="container">
<div class="grid">

<div class="box">
<h3>Latest Jobs</h3>
<ul id="jobsList"></ul>
</div>

<div class="box">
<h3>Results</h3>
<ul id="resultsList"></ul>
</div>

<div class="box">
<h3>Admit Card</h3>
<ul id="admitList"></ul>
</div>

</div>
</div>

<div class="admin" onclick="openAdmin()">ADMIN</div>

<div id="adminPanel">
<h2>Admin Panel</h2>
<select id="type">
<option value="jobs">Jobs</option>
<option value="results">Results</option>
<option value="admit">Admit Card</option>
</select>
<input type="text" id="title" placeholder="Enter Title">
<button onclick="addData()">Add</button>
<button onclick="closeAdmin()">Close</button>
</div>

<script>
let data = JSON.parse(localStorage.getItem("data")) || {jobs:[], results:[], admit:[]};

function render(){
  document.getElementById("jobsList").innerHTML = data.jobs.map(i=>`<li>${i}</li>`).join("");
  document.getElementById("resultsList").innerHTML = data.results.map(i=>`<li>${i}</li>`).join("");
  document.getElementById("admitList").innerHTML = data.admit.map(i=>`<li>${i}</li>`).join("");
}

function addData(){
  let type = document.getElementById("type").value;
  let title = document.getElementById("title").value;
  if(title.trim()==="") return alert("Enter title");
  data[type].unshift(title);
  localStorage.setItem("data", JSON.stringify(data));
  document.getElementById("title").value="";
  render();
}

function openAdmin(){document.getElementById("adminPanel").style.display="block";}
function closeAdmin(){document.getElementById("adminPanel").style.display="none";}

render();
</script>

</body>
</html>
