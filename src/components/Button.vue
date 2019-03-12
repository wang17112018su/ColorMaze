<template>
     <button class="button" v-on:click="changeCondition">{{ color }}</button>
</template>

<script>
export default {
  name: 'Button',

  props: {
    color: String,
  },
  methods: {
    changeCondition(){
        this.$emit('changeCondition', 'restart');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .button{
    padding: 25px;
    border: 2px solid black;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    width: 100px
  }

</style>
