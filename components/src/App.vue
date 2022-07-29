
<template>
  <h3>Hey!</h3>
  <greet :greetage="age" @updateFromGreet="updateFromGreetFn" ></greet>
  <user :age="age" :caravab="car" @age-change="updateAge" ></user>
</template>

<script>
import  Greet  from './components/Greet.vue'
import  User  from './components/User.vue'

  export default {
    name: 'App',
    components: {
      Greet,
      User
    },

    data() {
      return {
        age: 20,
        car: "mercedes"
      }
    },

    methods: {
      updateAge (num) {
        this.age += num 
      },

      updateFromGreetFn () {
        this.age ++
      }
    }
  }
</script>