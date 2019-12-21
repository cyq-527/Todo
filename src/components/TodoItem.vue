<template>
    <div>
        <li @click="click">{{content}}</li>
    </div>
</template>

<script>
    export default {
        name: "TodoItem",
        props:['content','index'],
        methods:{
            click()
            {
                this.$emit('delete',this.index)
            }
        }
    }
</script>

<style scoped>

</style>