
<template>
    <p v-if="greetage > 25"> {{ msg }} </p>
    <p v-else>You must be 25 to view</p>

    <button style="background-color: red; margin-right: 20px;" type="button" @click="updateAgeGreet">incrementGreet</button>
</template>

<script>
  export default {
    name: 'Greet',
    props: ["greetage"],
    emits: ['updateFromGreet'],

    data() {
      return {
        msg: "Hello World from Greet.vue"
      }
    },


    methods: {
        updateAgeGreet () {
            this.$emit('updateFromGreet')
        }
    },

  }
</script>

<style scoped lang="scss">
    p{
        color: blue;

        &:hover {
            color: darken(#cc4444, 15%);
        }
    }
</style>