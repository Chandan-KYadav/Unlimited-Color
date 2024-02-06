# Javascript code

``` Js
// Generate a random color

const randomColor = function () {
    const hex = '0123456789ABCDEF'
    let color = '#'

    for (let i = 0; i < 6; i++) {

        let value = Math.floor(Math.random() * 16)
        // color += hex(Math.floor(Math.random() * 16 ))
        color += hex[value]
    }
    return color
}

let intervalId 

function startChangingColor(){

    if(!intervalId){
        intervalId = setInterval(changeColor, 1000)
    }

    function changeColor(){

        document.body.style.backgroundColor = randomColor();

    }
}

function stopChangingColor(){

    clearInterval(intervalId)

    intervalId = null

}

document.querySelector('#start').addEventListener('click',startChangingColor)

document.querySelector('#stop').addEventListener('click',stopChangingColor)


```
