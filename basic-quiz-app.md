# Basic Quiz App

###HTML

```node
<!DOCTYPE html>
<html>
    <head>

        <title>Bipon Biswas</title>
        <link href ="style.css" rel ="stylesheet">
        <link href="https://fonts.googleapis.com/css?family=Lato" rel="stylesheet">
        <script src = "script.js"></script>

    </head>
    <body>
    <h2>This is basic quiz app in HTML/CSS/Javascript!</h2>

        <form id = "quiz" name = "quiz">

                <p class = "questions">What is the capital of Bangladesh?</p>
                <input id = "textbox" type = "text" name = "question1">

                <p class = "questions">What is the capital of India?</p>
                <input type = "radio" class = "radio" name = "question2" value = "Delli"> Delli<br>
                <input type = "radio" class = "radio" name = "question2" value = "Kolkata"> Kolkata<br>

                <p class = "questions">What is the capital of France?</p>

                <input type = "radio" class = "radio" name = "question3" value = "Paris"> Paris<br>
                <input type = "radio" class = "radio" name = "question3" value = "All Benny's"> All Benny's<br>

                <input id = "button" type = "button" value = "I'm finished!" onclick = "check();">

        </form>

        <div id = "after-submit">
            <p class="mt-10" id="correct-answer"></p>
            <h5 id="message"></h5>
            <img id="picture">
        </div>
    </body>
</html>
```

###CSS

```node
body {
	font-family: 'Lato', sans-serif;
}
.mt-10{
	margin-top: 10px;
}
#quiz {
	margin-left: 10px;
	background: #d2def2;
	padding: 10px 20px 10px 20px;
	width: 400px;
	float: left;
}
input {
	margin-bottom: 20px;
	display: block;
}
#textbox {
	height: 25px;
	font-size: 16px;
	border-radius: 5px;
	border: none;
	padding-left: 5px;
}
#button {
	background: green;
	border: none;
	border-radius: 5px;
	padding: 10px;
	color: white;
	font-size: 16px;
	transition-duration: .3s;
	margin-top: 15px;
}
#button:hover {
	background: #31ab31;
	cursor: pointer;
}
#after-submit {
	visibility: hidden;
	background: #ffa07c;
	padding: 10px 20px 10px 20px;
	width: 400px;
	float: left;
	margin-left: 20px;
	font-size: 30px;
}
#picture {
	width: 375px;
	height: 245px;
}
.radio {
	display: inline;
} 
```

###JS

```node
function check(){
		let question1 = document.quiz.question1.value;
		let question2 = document.quiz.question2.value;
		let question3 = document.quiz.question3.value;
		let afterSubmit = document.getElementById('after-submit');
		let correctAnwer = document.getElementById('correct-answer');
		let showMessage = document.getElementById('message');
		let photo = document.getElementById('picture');
		let correct = 0;

		if(question1 == "Dhaka"){
			correct++
		}
		if(question2 == "Delli"){
			correct++
		}
		if(question3 == "Paris"){
			correct++
		}

		let message = ['Great job man!','Just Okey!','You should need to improve.'];
		let pictures = ['img/win.gif', 'img/meh.gif', 'img/lose.gif']
		let range;

		if(correct < 1){
			range = 2;
		}
		if(correct > 0 && correct < 3){
			range = 1;
		}
		if(correct > 2){
			range = 0;
		}

		afterSubmit.style.visibility = 'visible';
		correctAnwer.innerHTML = 'You got ' + correct + ' correct answer'; 
		showMessage.innerHTML = message[range];
		photo.src = pictures[range];
	}
```