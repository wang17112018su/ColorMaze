<template>
    <div>
        <h3>Please choose the next button</h3>
        <Button class="white" color="White" v-on:changeCondition="changeBlackRed($event)"></Button>
        <Button class="orange" color="Orange" v-on:changeCondition="changeGreenOrangeBlack($event)"></Button>
    </div>
</template>

<script>
    import Button from "./Button";
    export default {
        name: "WhiteOrangePanel",
        components: {
            Button
        },
        methods: {
            changeBlackRed(updateCondition){
                this.$emit(updateCondition,2)
            },
            changeGreenOrangeBlack(updateCondition){
                this.$emit(updateCondition,4)
            }
        }
    }
</script>

<style scoped>
    .orange {
        background-color: orange; /* Black */
        color: white;
    }

    .white {
        background-color: #ffffff; /* White */
        color: black;
    }

</style>
