<template>
    <div>
        <h3>{{ title }}</h3>
        <Button class="green" color="Green" v-on:changeCondition="changeGreen($event)"></Button>
        <Button class="orange" color="Orange" v-on:changeCondition="changeOrange($event)"></Button>
        <Button class="black" color="Black" v-on:changeCondition="changeBlack($event)" ></Button>
    </div>

</template>

<script>
    import Button from "./Button";
    export default {
        name: "GreenOrangeBlackPanel",
        components: {Button},
        data(){
            return{
                title: "Please choose the next button",
                titleChanged: false,
                greenCounter: 0,
                orangeCounter: 0
            }
        },
        methods: {
            changeCondition(){
                if(this.titleChanged){
                    this.title= "Please choose the next button";
                }else{
                    this.title= "Next please";
                }
                this.titleChanged = !(this.titleChanged)
            },
            changeGreen(updateCondition){
                this.changeCondition();
                if(this.greenCounter==0 && this.orangeCounter==0){
                    this.greenCounter++;
                }else if (this.greenCounter==0 && this.orangeCounter==1){
                    this.$emit(updateCondition, 0);
                }else{
                    this.$emit(updateCondition, 1);
                }
            },
            changeOrange(updateCondition){
                this.changeCondition();
                if(this.greenCounter==0 && this.orangeCounter==0){
                    this.orangeCounter++;
                }else if (this.greenCounter==1 && this.orangeCounter==0){
                    this.$emit(updateCondition, 0);
                }else{
                    this.$emit(updateCondition, 1);
                }
            },
            changeBlack(updateCondition){
                if (this.greenCounter==1 || this.orangeCounter==1){
                    this.$emit(updateCondition, 0);
                }else{
                    this.changeCondition();
                }
            },
        }
    }
</script>

<style scoped>

    .green {
        background-color: green; /* Black */
        color: white;
    }

    .black {
        background-color: #000000; /* Black */
        color: white;
    }

    .orange {
        background-color: orange; /* Black */
        color: white;
    }

</style>
