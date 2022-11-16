<template>
  <div class="container">
    <Header title="Task Tracker" />

  </div>
</template>

<script>

import Header from './components/Header'

export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn{
    cursor: pointer;
    padding: 10px 20px;
    display: inline-block;
    border: none;
    margin: 5px;
    border-radius: 5px;
    text-decoration: none;
    font-size: 15px;
    font-family: inherit;
    background: #000;
    color: #fff;
}
</style>
