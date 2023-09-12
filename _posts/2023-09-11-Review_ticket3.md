---
toc: true
comments: false
layout: post
title: Review Ticket 3
description: Here I will be going over my accomplishments and troubles. 
type: tangibles
courses: { compsci: {week: 3} }
---

## Week 3:
 
This week we were preparing our pair showcase. Abdullah and I wanted to add a tetris or a quiz game using the help from our classmates and chat GPT. Then, we wanted to add our own elements to it to make it unique. However, that did not work out as planned. I ended up changing a game called "Guess My Number." I changed the number of inputs and outputs, as well as the background color, shadow and text font. Abdullah found another game too and I ended up copying it too and trying to edit it. 


## Main Troubles/Solutions: 

This week my main problem was finding a working source code for a quiz or tetris, which it seeemed like there never was. Then, I just gave up and found a game that I liked called "guess my number." It's honestly a cool game, and the design I added to it was pretty cool. However, that design didn't work till I actuallt ran "make clean." Thankfully, this week that was the main issue. 

## Comparing my games: 


<html>
<head>
    <title>Whack-a-Mole Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        #game-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
        #game-board {
            display: grid;
            grid-template-columns: repeat(3, 100px);
            grid-gap: 10px;
        }
        .hole {
            width: 100px;
            height: 100px;
            background-color: #009900;
            border: 2px solid #003300;
            border-radius: 50%;
            cursor: pointer;
            position: relative;
        }
        .mole {
            width: 60px;
            height: 60px;
            background-color: #660000;
            border: 2px solid #330000;
            border-radius: 50%;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
    </style>
</head>
<body>
    <div id="game-container">
        <h1>Whack-a-Mole Game</h1>
        <p>Click on the moles as they appear!</p>
        <div id="game-board">
            <div class="hole" onclick="whackMole(this)"></div>
            <div class="hole" onclick="whackMole(this)"></div>
            <div class="hole" onclick="whackMole(this)"></div>
            <div class="hole" onclick="whackMole(this)"></div>
            <div class="hole" onclick="whackMole(this)"></div>
            <div class="hole" onclick="whackMole(this)"></div>
            <div class="hole" onclick="whackMole(this)"></div>
            <div class="hole" onclick="whackMole(this)"></div>
            <div class="hole" onclick="whackMole(this)"></div>
        </div>
        <p id="message">Score: 0</p>
    </div>
    <script>
        let score = 0;
        let moleInterval;
        function getRandomHole() {
            const holes = document.querySelectorAll('.hole');
            const randomIndex = Math.floor(Math.random() * holes.length);
            return holes[randomIndex];
        }
        function popUpMole() {
            const hole = getRandomHole();
            const mole = document.createElement('div');
            mole.classList.add('mole');
            mole.addEventListener('click', () => {
                whackMole(mole);
            });
            hole.appendChild(mole);
            setTimeout(() => {
                hole.removeChild(mole);
            }, 1000);
        }
        function whackMole(mole) {
            if (mole.classList.contains('mole')) {
                mole.parentNode.removeChild(mole);
                score++;
                updateScore();
            }
        }
        function updateScore() {
            document.getElementById('message').textContent = `Score: ${score}`;
        }
        function startGame() {
            score = 0;
            updateScore();
            moleInterval = setInterval(popUpMole, 1000);
        }
        startGame();
    </script>
</body>
</html>


<img src ="images/Guess1.jpg">

<img src ="images/freeform.jpg"> 
