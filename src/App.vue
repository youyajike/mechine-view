<template>
  <div id="app">
    <Banner/>
    <img src="./assets/logo.png">
    <h1 :title="url">site : {{site}}</h1>
    <h1 v-if="seen">{{details}}</h1>
    <ol>
      <li v-for="todo in todos">
        {{ todo.text }}
      </li>
    </ol>
    <button @click="reverseMessage(buttonTxt)">{{buttonTxt}}</button>
    <input type="text" v-model="site"/>
  </div>
</template>

<script>/* eslint-disable space-before-function-paren */
import Banner from './components/Banner'

export default {
  name: 'App',
  components: {
    Banner
  },
  data() {
    return {
      site: '百度',
      url: 'http://www.baidu.com',
      details: '中国很强！',
      seen: false,
      buttonTxt: '点击反转',
      todos: [
        {text: '学习 JavaScript'},
        {text: '学习 Vue'},
        {text: '整个牛项目'}
      ]
    }
  },
  methods: {
    reverseMessage: function (data) {
      this.buttonTxt = data.split('').reverse().join('')
    }
  }
}

</script>

<style>
  body {
    margin: 0px;
    padding: 0px;
  }

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 0px;
  }

  #app img {
    padding-top: 60px;
  }
</style>
