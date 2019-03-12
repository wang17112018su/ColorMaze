<template>
    <div>
        <h3> You Win! Congratulations!!</h3>
        <Button color="Restart" v-on:changeCondition="changeCondition($event)"></Button>
    </div>
</template>

<script>
    import Button from "./Button";
    export default {
        name: "YouWin",
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
