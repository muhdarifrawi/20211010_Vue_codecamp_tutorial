# 20211010 Vue Tutorial

## Preface
This tutorial is done by following [Vue.js Course for Beginners [2021 Tutorial]](https://youtu.be/FXpIoQ_rT_c) by Gwendolyn Faraday.

## Setup

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

## Directive
Directives are a way for your `HTML` elements to connect to `Vue.js` scripts.

```html
<input v-model="greeting"/>
```
Directives in `Vue.js` looks like a `HTML` attribute. But they start with `v-`. In the above instance, `v-model` is being used. What this would do is bind the variable that was passed as an argument into `v-model` to be used in `HTML`. The `input` would start with what was in the `greeting` variable and as you type, the `greeting` text changes as well. This is known as two-way data binding and is handled by `Vue.js` via the `v-model` directive.

```html
<div class="box" v-if="isVisible"></div>
```
```js
let app = Vue.createApp()({
    data:function(){
        return{
            greeting: "Hello world",
            isVisible: true
        }
    }
})

app.mount("#app")
```
`v-if` works like how a normal `if-else` statement would work. It takes in a boolean data type. If the boolean is set to `false`, then that whole element would not be rendered. There is an alternative directive that we can use if we wish to reduce script latency. 

```html 
<div class="box" v-show="isVisible"></div>
```
`v-show` is almost similar to `v-if`. Takes in a boolean data type. However, instead of not rendering when set to `false`, it would actually change style display to `display:none;`.

Most of the time you would use `v-if`. For things like loading spinner/icon, where it would only show up for that particular purpose and disappear. `v-show` however, would be for things where you would toggle often. Hiding the element would be more performant than having to create and delete the DOM often. 

```html
<div class="box" v-if="isVisible"></div>
<div class="box-2" v-else-if="isVisible2"></div>
<div class="box-3" v-else></div>
```
For a `v-if` directive, as mentioned, it works like any `if-else` statement. The `v-else-if` would also take in an argument while the `v-else` would not need to. 

```html
<div id="app" v-cloak>
    {{ greeting}}
</div>
```
```css
[v-cloak]{
    display:none;
}
```
`v-cloak` is another useful directive. Most of the time you may not need to use it. What this does is to "hide" your element with a CSS script until `Vue.js` has rendered the particular variable. By defualt, it would have already done that. But in the case where you see your variables appear with the curly brackets `{{ }}` as it renders, you may want to use `v-cloak`.