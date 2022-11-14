<template>
    <div>
     <h1>
        Post Component with Vue Js
     </h1>
     <form @submit="submitData" method="post">
        <input type="text" name="title" v-model="post.title"/><br><br>
        <input type="text" name="author" v-model="post.author"/><br><br>
        <button type="submit">Post</button>
     </form>
     <div>
     
     </div>
    </div>
</template>
<script>
import Vue from 'vue';   ///this is the important linking part
import axios from 'axios'
import VueAxios from 'vue-axios'
Vue.use(VueAxios,axios)
export default {
    name:'PostComponent',
    data(){
        return {
            post:{
           title:null,
           author:null,
        }
    }
    }
    ,methods:{
        submitData(e){
            this.axios.post('http://localhost:3000/posts',this.post).then((resp)=>{  //replace this link with the original API link
                console.warn("result",resp)
            })
            console.warn(this.post)           
            e.preventDefault();

        }
    }

}
</script>
