# 20211010 Vue Tutorial

## Preface
This tutorial is done by following [Vue.js Course for Beginners [2021 Tutorial]](https://youtu.be/FXpIoQ_rT_c) by Gwendolyn Faraday.

## Basics

```js
let app = Vue.createApp()({
    data:function(){
        return{
            greeting: "Hello world"
        }
    }
})

app.mount("#app")
```

`Vue` is the variable that can be used after importing `Vue.js` package. 
`createApp()` is the method of it. 
It basically lets you create your vue application and you can pass it an <b>options object</b> such as `data`. Any variable or functions will live in this area.

`data` is a function that returns an object. In the object we return, we have `greeting` as our variable and it is holding a string "Hello world".

Storing it into variable `app` allows you to call the code and use another method on it.
In this instance, `.mount()` was used to mount it into `HTML`. It would look for the id "app" in `HTML`.