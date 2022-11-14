<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->

  <h1 style="font-size:40px">{{title}}</h1>
  <HomeComponent />
  <DataBind/>
  <ChildComponent v-on:changeTitle="updateTitle($event)"/>

  <br>
  <br>
  <br>
  <h1 style="font-size=100px">FORMS START HERE</h1>

  <!-- <SignUp/> -->
  <br>
  <br>
  <br>
  <br>
  <br>
 <h1>Login Begins here</h1>
<LoginComponent/>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import DataBind from './components/DataBind.vue'
import HomeComponent from './components/HomeComponent.vue'
import ChildComponent from './components/ChildComponent.vue'
// import SignUp from './components/SignUp.vue'
import LoginComponent from './components/LoginComponent.vue'
export default {
  name: 'App',
  components: {
    // HelloWorld,
    HomeComponent,
    DataBind,
    ChildComponent,
    // SignUp,
    LoginComponent,

  },
  data(){
    return{
    title:"Props Tutorial Change Title",
    }
  },
    methods:{
      updateTitle(title){
        this.title = title
      }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
