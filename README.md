<!-- ================= FILE 1: index.html ================= --><!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Study Buddy Finder</title>
<link rel="stylesheet" href="style.css">
</head>
<body><div class="container">
    <h2>Study Buddy Finder 📚</h2><input type="text" id="name" placeholder="Enter your name">

<select id="subject">
    <option value="">Select Subject</option>
    <option>Math</option>
    <option>Science</option>
    <option>Programming</option>
</select>

<select id="time">
    <option value="">Preferred Time</option>
    <option>Morning</option>
    <option>Evening</option>
</select>

<button onclick="addUser()">Sign Up</button>
<button onclick="findBuddy()">Find Buddy</button>

<div class="result" id="result"></div>

</div><script src="script.js"></script></body>
</html><!-- ================= FILE 2: style.css ================= -->body { font-family: Arial, sans-serif; background: linear-gradient(to right, #74ebd5, #9face6); margin: 0; } .container { max-width: 400px; margin: 50px auto; background: white; padding: 20px; border-radius: 15px; box-shadow: 0 5px 15px rgba(0,0,0,0.2); } h2 { text-align: center; } input, select, button { width: 100%; padding: 10px; margin: 10px 0; border-radius: 8px; border: 1px solid #ccc; } button { background: #6a11cb; color: white; border: none; cursor: pointer; } button:hover { background: #2575fc; } .result { margin-top: 15px; padding: 10px; background: #f1f1f1; border-radius: 8px; }

<!-- ================= FILE 3: script.js ================= -->let users = [];

function addUser() { let name = document.getElementById("name").value; let subject = document.getElementById("subject").value; let time = document.getElementById("time").value;

if(name === "" || subject === "" || time === ""){
    alert("Please fill all fields");
    return;
}

users.push({name, subject, time});
alert("Signup Successful!");

}

function findBuddy() { let subject = document.getElementById("subject").value; let time = document.getElementById("time").value; let resultDiv = document.getElementById("result");

let found = users.filter(user => user.subject === subject && user.time === time);

if(found.length > 0) {
    resultDiv.innerHTML = "Buddy Found: " + found.map(u => u.name).join(", ");
} else {
    resultDiv.innerHTML = "No buddy found";
}

}# Study-buddy-finder
