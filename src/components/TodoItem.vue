<template>
    <div :class="typeclass">
        <h1>{{title}}</h1>
       <ul>
           <li v-for="(item,index) in list" :key="index" @click="handle(index)">{{item}}</li>
       </ul>
    </div>
</template>

<script>
    export default {
        name: "TodoItem",
        props:{
            list:{
                type:Array
            },
            listType:{
                type: Boolean,
                default:false
            },
            title:[String]
        },
        methods:{
            handle(index)
            {
                if(!this.listType)
                   this.$emit('addDone',index);
                else
                   this.$emit('delete',index)
            }
        },
        computed:{
            typeclass()
            {
                return this.listType?'redcolor':'bluecolor';
            }
        }
    }
</script>

<style scoped>
 .redcolor{
     background: palevioletred;
 }
 .bluecolor{
        background: aqua;
    }
</style>