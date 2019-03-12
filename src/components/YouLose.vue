<template>
    <div>
        <h3> Game Over! Try again?</h3>
        <Button color="Restart" v-on:changeCondition="changeCondition($event)"></Button>
    </div>
</template>

<script>
    import Button from "./Button";
    export default {
        name: "YouLose",
        components: {Button},
        methods: {
            changeCondition(updateCondition){
                this.$emit(updateCondition,-1);
            }
        }
    }
</script>

<style scoped>

</style>
