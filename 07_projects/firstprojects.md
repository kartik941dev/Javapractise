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

