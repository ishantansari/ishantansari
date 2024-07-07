<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cat Walking and Talking</title>
    <style>
        #cat {
            width: 200px;
            height: 200px;
            background: url('cat.png') no-repeat;
            background-size: cover;
        }
    </style>
</head>
<body>
    <div id="cat"></div>
    <div>
        <button onclick="feedCat()">Feed</button>
        <button onclick="groomCat()">Groom</button>
    </div>
    <div id="message"></div>

    <script src="cat.js"></script>
</body>
</html>
let catMood = 5; // Initial mood level of the cat

function feedCat() {
    catMood += 2;
    showMessage("You fed the cat.");
    updateCatMood();
}

function groomCat() {
    catMood += 1;
    showMessage("You groomed the cat.");
    updateCatMood();
}

function showMessage(message) {
    document.getElementById("message").innerText = message;
}

function updateCatMood() {
    // Update cat's image based on mood level
    let catElement = document.getElementById("cat");
    if (catMood >= 8) {
        catElement.style.backgroundImage = "url('happy_cat.png')";
    } else if (catMood >= 5) {
        catElement.style.backgroundImage = "url('normal_cat.png')";
    } else {
        catElement.style.backgroundImage = "url('sad_cat.png')";
    }
}
