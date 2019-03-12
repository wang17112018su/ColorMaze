<template>
    <div>
        <h3>Please choose a button</h3>
        <Button class="white" color="White" v-on:changeCondition="changeWhiteOrange($event)"></Button>
        <Button class="red" color="Red" v-on:changeCondition="changeBlackRed($event)"></Button>
    </div>

</template>

<script>
    import Button from "./Button.vue";
    export default {
        name: "StartPanel",
        components: {
            Button

        },
        methods: {

            changeBlackRed(updateCondition){
                this.$emit(updateCondition,2)
            },
            changeWhiteOrange(updateCondition){
                this.$emit(updateCondition,3)
            }
        }
    }
</script>

<style scoped>
    .red {
        background-color: red;
        color: white;
    }

    .white {
        background-color: #ffffff; /* White */
        color: black;
    }

</style>
