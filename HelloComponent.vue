<template>
    <div>

        <h1> Home Component </h1>
        <p  v-html="rowHtml"></p>

            <h2>{{name}}</h2>
        <h2 v-once>{{name}}</h2>
        <button v-on:click="updateText">Push Me!!</button>
        <button v-bind:disabled="disableBtn"  v-on:click="updateText">Push Me tWICE!!</button>
        <h3>{{ok?"Yes":"No"}}</h3>
        <h1 v-bind:style="{color:'red'}">Style Binding</h1>

        <h1 v-bind:class="{display:show}">Style Binding</h1>
        <h1 v-bind:class="[aclass]">Class Tria Style Binding</h1>
        <UsersComponent/>
        <ProductsComponent/>
       
        

    </div>
</template>
<script>
import UsersComponent from './UsersComponent.vue';
import ProductsComponent from './ProductsComponent.vue';
export default {
  components: { UsersComponent, ProductsComponent },
    name:'HomeComponent',
    data(){
        return {
            name:'Lucifer',
            ok:true,
            rowHtml:"<h1>template in Vue Js</>",
            disableBtn:false,
            show:true,
            aclass:'arrayClass',
        }
    },
    methods:{
        updateText(){
        this.name='Nishu';
        this.ok = !this.ok;
        },
        
    }

    
}
</script>

<style scoped>
div{
    background-color: aquamarine;
    height: 500px;
   
}
.display{
    background-color: yellow;
}
.arrayClass{
    background-color: cyan;
}
</style>
