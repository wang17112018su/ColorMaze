<template>
    <div>
        <h3>Please choose the next button</h3>
        <Button class="red" color="Red" v-on:changeCondition="changeCondition($event)"></Button>
        <Button class="black" color="Black" v-on:changeCondition="changeGreenOrangeBlack($event)"></Button>
    </div>

</template>

<script>
    import Button from "./Button.vue";
    export default {
        name: "BlackRedPanel",
        components: {
            Button
        },
        methods: {
            changeCondition(updateCondition) {
                this.$emit(updateCondition, 0)
            },
            changeGreenOrangeBlack(updateCondition) {
                this.$emit(updateCondition, 4)
            },
        }
    }
</script>

<style scoped>
    .red {
        background-color: red;
        color: white;
    }

    .black {
        background-color: #000000; /* Black */
        color: white;
    }

</style>
