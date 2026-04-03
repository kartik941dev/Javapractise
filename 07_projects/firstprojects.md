# projects related to DOM

## projects link
[click here](https://stackblitz.com/edit/vitejs-vite-gcpw9hjo?file=index.html&terminal=dev)
[click here](https://stackblitz.com/edit/dom-project-chaiaurcode?file=1-colorChanger%2Findex.html,1-colorChanger%2Fchaiaurcode.js)
# solution code

## PROJECT 1 SOLUTION

```javascript
console.log("Kartik")
const buttons = document.querySelectorAll('.button')
const body = document.querySelector("body")

buttons.forEach(function (button){
  console.log(button);
  //setting events
  button.addEventListener('click',function(e){
    console.log(e)
    console.log(e.target)
    if(e.target.id == 'grey'){
      body.style.backgroundColor = e.target.id
    }
    if(e.target.id == 'yellow'){
      body.style.backgroundColor = e.target.id
    }
    if(e.target.id == 'white'){
      body.style.backgroundColor = e.target.id
    }
    if(e.target.id == 'blue'){
      body.style.backgroundColor = e.target.id
    }
  })
});
```
## PROJECT 2 SOLUTION

``` javascript

const form = document.querySelector('form')

//this use case will give u empty value 
// const height = parseInt(document.querySelector('#height').value)


form.addEventListener('submit', function (e){
  e.preventDefault()

  const height = parseInt(document.querySelector('#height').value)
  const weight = parseInt(document.querySelector('#weight').value)
  const results = document.querySelector('#results')


  if(height === '' || height < 0 || isNaN(height)){
    results.innerHTML = `Please give valid height ${height}`;
  } else if(weight === '' || weight < 0 || isNaN(weight)){
    results.innerHTML = `Please give valid weight ${weight}`;
  } 
    // const bmi = (weight / ((height*weight)/1000)).toFixed(2)
    // const bmi = (weight / ((height * height) / 10000)).toFixed(2);
    // // show the result
    // results.innerHTML = `<span>${bmi}<span>`;
    // if (results.innerHTML >= 24.9){
    //   console.log("OVERWEIGHT")
    // }
    // else if (results.innerHTML<18.6){
    // }

    else {
      const bmi = (weight / ((height * height) / 10000)).toFixed(2);
  
      if (bmi < 18.6) {
          results.innerHTML = `<span>${bmi} - Underweight</span>`;
      } 
      else if (bmi >= 18.6 && bmi <= 24.9) {
          results.innerHTML = `<span>${bmi} - Normal</span>`;
      } 
      else {
          results.innerHTML = `<span>${bmi} - Overweight</span>`;
      }
  }
});
```

## PROJECT 3 SOLUTION
``` javascript

const clock = document.querySelector('#clock')
setInterval(function(){
  let date = new Date()
 // console.log(date.toLocaleDateString)

 clock.innerHTML = date.toLocaleTimeString();
},1000);

```

## PROJECT 4 SOLUTION

``` javascript

let randomNumber = parseInt(Math.random() * 100 + 1);

const submit = document.querySelector('#subt');
const userInput = document.querySelector('#guessField');
const guessSlot = document.querySelector('.guesses');
const remaining = document.querySelector('.lastResult');
const lowOrHi = document.querySelector('.lowOrHi');
const startOver = document.querySelector('.resultParas');

const p = document.createElement('p');

let prevGuess = [];
let numGuess = 1;

let playGame = true;

if (playGame) {
  submit.addEventListener('click', function (e) {
    e.preventDefault();
    const guess = parseInt(userInput.value);
    console.log(guess);
    validateGuess(guess);
  });
}

function validateGuess(guess) {
  if (isNaN(guess)) {
    alert('PLease enter a valid number');
  } else if (guess < 1) {
    alert('PLease enter a number more than 1');
  } else if (guess > 100) {
    alert('PLease enter a  number less than 100');
  } else {
    prevGuess.push(guess);
    if (numGuess === 11) {
      displayGuess(guess);
      displayMessage(`Game Over. Random number was ${randomNumber}`);
      endGame();
    } else {
      displayGuess(guess);
      checkGuess(guess);
    }
  }
}

function checkGuess(guess) {
  if (guess === randomNumber) {
    displayMessage(`You guessed it right`);
    endGame();
  } else if (guess < randomNumber) {
    displayMessage(`Number is TOOO low`);
  } else if (guess > randomNumber) {
    displayMessage(`Number is TOOO High`);
  }
}

function displayGuess(guess) {
  userInput.value = '';
  guessSlot.innerHTML += `${guess}, `;
  numGuess++;
  remaining.innerHTML = `${11 - numGuess} `;
}

function displayMessage(message) {
  lowOrHi.innerHTML = `<h2>${message}</h2>`;
}

function endGame() {
  userInput.value = '';
  userInput.setAttribute('disabled', '');
  p.classList.add('button');
  p.innerHTML = `<h2 id="newGame">Start new Game</h2>`;
  startOver.appendChild(p);
  playGame = false;
  newGame();
}

function newGame() {
  const newGameButton = document.querySelector('#newGame');
  newGameButton.addEventListener('click', function (e) {
    randomNumber = parseInt(Math.random() * 100 + 1);
    prevGuess = [];
    numGuess = 1;
    guessSlot.innerHTML = '';
    remaining.innerHTML = `${11 - numGuess} `;
    userInput.removeAttribute('disabled');
    startOver.removeChild(p);

    playGame = true;
  });
}

```
## BASIC TRY PROJECT COMPLETED
