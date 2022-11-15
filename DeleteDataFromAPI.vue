<template>
    <div>
        <h1>
            Users Component Starts Here
        </h1>
        <table style="border:2px;">
        <tr>
            <td>
                Name
            </td>
            <td>
                Email
            </td>
            <td>
                Address
            </td>
            <td>
                Action
            </td>
        </tr>
        <tr v-for="user in users" v-bind:key="user.id">
            <td>
                {{user.author}}
            </td>
            <td>
                {{user.id}}

            </td>
            <td>
                {{user.title}}
            </td>
            <td>
                <button v-on:click="deleteUser(user.id)">Delete</button>
            </td>
        </tr>
    </table>
    </div>
</template>
<script>
import Vue from 'vue';
import axios from 'axios'
import VueAxios from 'vue-axios'
Vue.use(VueAxios,axios)
export default {
    name:'UsersComponent',
    data(){
        return{
            users:null,

        }
    },
    methods:{
      getUsers(){
        this.axios.get("http://localhost:3000/posts/").then(result=>{
            console.warn(result)
            this.users = result.data;
        }
      )},
      deleteUser(id){
          this.axios.delete("http://localhost:3000/posts/"+id).then(result=>{
              console.warn(result)
              this.getUsers();
  
          }
        )
      },
    },
    mounted(){
         this.getUsers();

    }
}
</script>
