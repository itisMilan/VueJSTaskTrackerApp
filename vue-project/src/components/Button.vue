<template>
    
    <button @click="onclick()"
    
    v-bind:style="{background:color}" class="btn">{{ text }}</button>
</template>


<script>
export default{
    name:"Button",
    props:{
        text:String,
        color:String
    },
    methods:{
        onclick(){
          this.$emit('btn-click')
        }
    }
}</script>