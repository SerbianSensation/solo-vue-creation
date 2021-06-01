<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>{{ title }}</h1>
  <div class="container">
    <h2>Number of button clicks: {{ count }}</h2>
    <Button
          @btn-click="incCount()"
          :text="'Click Me!'"
          :color="count % 2 == 0 ? '#00FFFF' : '#006400'"
    />
  </div>

  <div class="container">
      <h3>Users:</h3><br>
      <Users />
  </div>

  <div class="container">
      <h3>Register:</h3><br>
      <addPerson />
  </div>
</template>

<script>
import Button from './components/Button'
import Users from './components/Users'
import addPerson from './components/addPerson'

export default {
  name: 'App',
  components: {
    Button,
    Users,
    addPerson,
  },
  data() {
    return {
        title: 'Stefan Gligorevic First Vue Project',
        count: 0,
    }
  },
  methods: {
    incCount: function() {
        this.count += 1;
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 650px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
