# projects related to DOM

## projects link
[click here](https://stackblitz.com/edit/vitejs-vite-gcpw9hjo?file=index.html&terminal=dev)

# solution code

## project 1

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