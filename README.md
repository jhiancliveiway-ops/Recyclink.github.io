Trash for Goods
<Trash for Goods>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Point Redeemer</title>

<style>
body{
    font-family: Franklin Gothic;
    background:#868282;
    text-align:center;
    margin-top:100px;
}

.container{
    background:gray;
    width:300px;
    margin:auto;
    padding:20px;
    border-radius:10px;
    box-shadow:0px 0px 10px rgba(0,0,0,0.2);
}

input{
    padding:10px;
    width:80%;
    margin-top:10px;
}

button{
    padding:10px 20px;
    margin-top:10px;
    cursor:pointer;
}

#message{
    margin-top:10px;
    font-weight:bold;
}
</style>

</head>

<body>

<div class="container">

<h2>Redeem Points</h2>

<p>Your Points: <span id="points">0</span></p>

<input type="text" id="codeInput" placeholder="Enter Code">

<br>

<button onclick="redeemCode()">Redeem</button>

<p id="message"></p>

</div>

<script>

let points = 0;

let codes = {
    "78F5":0.10,
    "65F6":0.10,
    "57T4":0.10,
    "55G5":0.10,
    "66F8":0.10,
    "79F1":0.10,
    "89F3":0.10
    
};

let usedCodes = [];

function redeemCode(){

    let input = document.getElementById("codeInput").value.toUpperCase();
    let message = document.getElementById("message");

    if(usedCodes.includes(input)){
        message.innerHTML = "Code already used!";
        message.style.color = "red";
        return;
    }

    if(codes[input]){

        points += codes[input];
        document.getElementById("points").innerHTML = points;

        usedCodes.push(input);

        message.innerHTML = "Success! +" + codes[input] + " points";
        message.style.color = "green";

    }else{

        message.innerHTML = "Invalid Code";
        message.style.color = "red";

    }

}

</script>

</body>
</html>
