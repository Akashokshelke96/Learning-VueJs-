<template>
    <div>
        <h1>
            Child Component
        </h1>
        <h3 v-for="user in users" :key="user.name">
        {{user.name}} -- {{user.email}}</h3>
      
        <button v-on:click="updateTitle"> Update Parent Title</button>
    </div>
</template>

<script>
export default {
    name:'ChildComponent',
    props:[
        'users'
    ],
    methods:{
        updateTitle(){
            this.$emit('changeTitle',"Parent Updated")
        }
    }

}
</script>
