<template>
    <div>
        <input type="text" v-model="value">
        <button @click="addItem">submit</button>
    </div>
</template>

<script>
    export default {
        name: "InputItem",
        data(){
            return{
                value:''
            }
        },
        methods:{
            addItem()
            {
                this.$emit('addItem',this.value);
                this.value=''
            }
        }
    }
</script>

<style scoped>

</style>