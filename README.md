* * * * * * * * * * * * * 
# Vue 3 & Pinia Counter App
* * * * * * * * * * * * * 

### 1. Create & Go into the Project folder
`cd Vue-3-Pinia-Counter`  
### 2.  Initialize Vue 
`npm init vue@latest`   

### 3. Install the following packages:  

`create-vue@latest`  
Ok to proceed? (y) y  
Vue.js - The Progressive JavaScript Framework

✔ Project name: … vue-3-pinia-counter  
✔ Add TypeScript? … No! / Yes  
✔ Add JSX Support? … No! / Yes  
✔ Add Vue Router for Single Page Application development? … No / Yes!  
✔ Add Pinia for state management? … No / Yes!  
✔ Add Vitest for Unit Testing? … No / Yes  
✔ Add Cypress for both Unit and End-to-End testing? … No / Yes  
✔ Add ESLint for code quality? … No! / Yes  

Scaffolding project in /Users/..PATH TO FOLDER../Vue-3-Pinia-Counter/vue-3-pinia-counter...  
DONE. NOW RUN :  
`cd vue-3-pinia-counter`  
`npm install`  
`npm run dev`  
### 4. In VS Code open project folder  
This is just the basic starting point.  
1. Inside `HomeView.vue` & `AboutView.vue` put : `class : home & about` and `H1 : Home & About`  
```html
| HomeView.vue      | AboutView.vue         |
|-------------------|-----------------------|
|<template>         | <template>            |
|<div class="home"> | <div class="about">   |
|<h1>Home</h1>      | <h1>About</h1>        |
|</div>             | </div>                |
|</template>        | </template>           |
```
2. Inside `App.view` :  
- Remove the `script` section & `style` section.  
Then put the code inside:       
```html
# App.vue:  
<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
<div class="app">
  <nav>
    <RouterLink to="/">Home</RouterLink> | 
    <RouterLink to="/about">About</RouterLink>
  </nav>

<RouterView />
</div>

</template>

<style>
.app {
  text-align: center;
}
.app nav {
  font-size: 20px;
}
</style>
```
3. Inside `HomeView.vue` :  
- Remove the `script` section & `style` section.  
Then put the code inside:   

```html 
# HomeView.vue: 
<template>
<div class="home">
<Counter />
  <div class="buttons">
    <button @click="storeCounter.decreaseCount">-</button>
    <button @click="storeCounter.increaseCount">+</button>
  </div>
  <hr />
  <h3>This number is: {{ storeCounter.oddOrEven }}</h3>
</div>
<hr />
  <h3>Edit counter:</h3>
<div>
  <input
    v-model="storeCounter.count"
    type="number">
</div>

</template>

<script setup>
import Counter from '@/components/Counter.vue'
import { useCounterStore } from '@/stores/counter'

const storeCounter = useCounterStore()  
</script>

<style>
.count {
  font-size: 60px;
  margin: 20px;
}
.buttons button {
font-size: 40px;
margin: 10px;
}
</style>
```

#### 4. `Counter.vue` from components folder  

```html
# components/Counter.vue:  
<template>
  <div class="count">
    {{ storeCounter.count }}
  </div>
</template>

<script setup>
import { useCounterStore } from '@/stores/counter'

const storeCounter = useCounterStore()  
</script>
```

#### 5. `counter.js` from stores folder  

```html
# stores/counter.js:  
import { defineStore } from 'pinia'

export const useCounterStore = defineStore({
  id: 'counter',
  state: () => ({
    count: 0
  }),
  actions: {
    increaseCount() {
      this.count++
    },
    decreaseCount() {
      this.count--      
    }
  }, 
  getters: {
    oddOrEven: (state) => {
      if (state.count % 2 === 0) return 'Even'
      return 'Odd'
    }
  },
})
```

## -> VS Code extensions important :  

#### 1. Split HTML Attributes (Vue, React, Angular) for VS Code ||  
Danny Connell  
https://marketplace.visualstudio.com/items?itemName=Equinusocio.vsc-material-theme  
Split your Vue, React & Angular directives & props (and HTML attributes) onto new lines, instantly!  
Tired of manually splitting your HTML attributes (or Vue.js / React / Angular directives & props) up onto multiple lines? You can now do it instantly with this extension:  
Usage:  
*→ Just select your opening (or self-closing) tag - from the opening angle bracket `(<) up to the closing angle bracket (>)` and either:* 
1) Open Command Pallette (CMD/CTRL + Shift + P) and choose Split HTML Attributes
2) Or use the keyboard shortcut (which defaults to `Ctrl + Alt + Shift + A` )  
#### 2. Incrementor ||  
Neil Smith  
https://marketplace.visualstudio.com/items?itemName=nmsmith89.incrementor  
- Keybindings
For now, default keybindings aren't being included but these are the ones I use.
```json
{
    "command": "incrementor.incrementByOne",
    "key": "ctrl+up"
},
{
    "command": "incrementor.decrementByOne",
    "key": "ctrl+down"
},
{
    "command": "incrementor.incrementByTenth",
    "key": "ctrl+shift+alt+up"
},
{
    "command": "incrementor.decrementByTenth",
    "key": "ctrl+shift+alt+down"
},
{
    "command": "incrementor.incrementByTen",
    "key": "ctrl+shift+up"
},
{
    "command": "incrementor.decrementByTen",
    "key": "ctrl+shift+down"
}
```
Known Issues:  
-When using the redo command (e.g. cmd+shift+z) the selections can get a little wonky. I have no idea why it does that but I am looking for a solution.  
-Undo works as expected.  

#### 3-1 Material Theme ||  
Equinusocio  
https://marketplace.visualstudio.com/items?itemName=Equinusocio.vsc-material-theme  

#### *3-2 Material Theme || -> NOW USING THIS ONE !!!*  
Equinusocio  
https://marketplace.visualstudio.com/items?itemName=Equinusocio.vsc-material-theme  

#### 4. Quick and Simple Text Selection  
David Bankier  
https://marketplace.visualstudio.com/items?itemName=dbankier.vscode-quick-select  

#### 4. Insert Numbers ||  
Asuka  
https://marketplace.visualstudio.com/items?itemName=Asuka.insertnumbers  


* * * * * * * * * * * * * 

* * * * * * * * * * * * * 



# Default README.md file, self-populated: vue-3-pinia-counter

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```
