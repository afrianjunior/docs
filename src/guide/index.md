---
title: Memulai
type: guide
order: 1
---

<!-- Let's start with a quick tour of Vue's data binding features. If you are more interested in a high-level overview first, check out this [blog post](http://blog.evanyou.me/2015/10/25/vuejs-re-introduction/). -->
Mari kita mulai dengan tour ringkas penggunaan fitur data binding pada Vue.js. Jika anda lebih tertarik untuk ikhtisar yang lebih tinggi levelnya, cek [postingan blog ini](http://blog.evanyou.me/2015/10/25/vuejs-re-introduction/).

<!-- The easiest way to try out Vue.js is using the [JSFiddle Hello World example](https://jsfiddle.net/yyx990803/okv0rgrk/). Feel free to open it in another tab and follow along as we go through some basic examples. If you prefer downloading / installing from a package manager, check out the [Installation](/guide/installation.html) page. -->
Cara termudah untuk mencoba Vue.js adalah melalui [contoh Hello World pada JSFiddle](https://jsfiddle.net/yyx990803/okv0rgrk/). Silakan membuka tab baru dan ikuti sebagaimana yang telah kami contohkan.

### Hello World

``` html
<div id="app">
  {{ message }}
</div>
```
``` js
new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue.js!'
  }
})
```
{% raw %}
<div id="app" class="demo">
  {{ message }}
</div>
<script>
new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue.js!'
  }
})
</script>
{% endraw %}

<!-- ### Two-way Binding -->
### Data Binding Dua Arah

``` html
<div id="app">
  <p>{{ message }}</p>
  <input v-model="message">
</div>
```
``` js
new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue.js!'
  }
})
```
{% raw %}
<div id="app2" class="demo">
  <p>{{ message }}</p>
  <input v-model="message">
</div>
<script>
new Vue({
  el: '#app2',
  data: {
    message: 'Hello Vue.js!'
  }
})
</script>
{% endraw %}

### Render sebuah List

``` html
<div id="app">
  <ul>
    <li v-for="todo in todos">
      {{ todo.text }}
    </li>
  </ul>
</div>
```
``` js
new Vue({
  el: '#app',
  data: {
    todos: [
      { text: 'Belajar JavaScript' },
      { text: 'Belajar Vue.js' },
      { text: 'Buat sesuatu yang mengagumkan' }
    ]
  }
})
```
{% raw %}
<div id="app3" class="demo">
  <ul>
    <li v-for="todo in todos">
      {{ todo.text }}
    </li>
  </ul>
</div>
<script>
new Vue({
  el: '#app3',
  data: {
    todos: [
      { text: 'Belajar JavaScript' },
      { text: 'Belajar Vue.js' },
      { text: 'Buat sesuatu yang mengagumkan' }
    ]
  }
})
</script>
{% endraw %}

<!-- ### Handle User Input -->
### Menangani Inputan dari Pengguna

``` html
<div id="app">
  <p>{{ message }}</p>
  <button v-on:click="reverseMessage">Balik Pesan</button>
</div>
```
``` js
new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue.js!'
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  }
})
```
{% raw %}
<div id="app4" class="demo">
  <p>{{ message }}</p>
  <button v-on:click="reverseMessage">Balik Pesan</button>
</div>
<script>
new Vue({
  el: '#app4',
  data: {
    message: 'Hello Vue.js!'
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  }
})
</script>
{% endraw %}

<!-- ### All Together Now -->
### Lakukan Secara Bersamaan

``` html
<div id="app">
  <input v-model="newTodo" v-on:keyup.enter="addTodo">
  <ul>
    <li v-for="todo in todos">
      <span>{{ todo.text }}</span>
      <button v-on:click="removeTodo($index)">X</button>
    </li>
  </ul>
</div>
```
``` js
new Vue({
  el: '#app',
  data: {
    newTodo: '',
    todos: [
      { text: 'Add some todos' }
    ]
  },
  methods: {
    addTodo: function () {
      var text = this.newTodo.trim()
      if (text) {
        this.todos.push({ text: text })
        this.newTodo = ''
      }
    },
    removeTodo: function (index) {
      this.todos.splice(index, 1)
    }
  }
})
```
{% raw %}
<div id="app5" class="demo">
  <input v-model="newTodo" v-on:keyup.enter="addTodo">
  <ul>
    <li v-for="todo in todos">
      <span>{{ todo.text }}</span>
      <button v-on:click="removeTodo($index)">X</button>
    </li>
  </ul>
</div>
<script>
new Vue({
  el: '#app5',
  data: {
    newTodo: '',
    todos: [
      { text: 'Add some todos' }
    ]
  },
  methods: {
    addTodo: function () {
      var text = this.newTodo.trim()
      if (text) {
        this.todos.push({ text: text })
        this.newTodo = ''
      }
    },
    removeTodo: function (index) {
      this.todos.splice(index, 1)
    }
  }
})
</script>
{% endraw %}

I hope this gives you a basic idea of how Vue.js works. I'm sure you also have many questions now - read along, and we will cover them in the rest of the guide.
Kami harap ini dapat memberikan Anda gambaran bagaimana Vue.js bekerja. Kami yakin anda juga memiliki banyak pertanyaan sekarang. Silakan baca terus, dan kami akan membahasnya di panduan berikutnya.
