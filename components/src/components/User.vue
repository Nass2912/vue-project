<template>
    <button type="button" @click="onClickAge">increment</button>

    <p v-if="age < 30">The user is {{ age }} years old and drives {{ caravab }} From user.vue</p>
    <p v-else>Too old sorry</p>
    <p> {{ ageDoubled }}</p>
</template>

<script>
    export default {
        name: "User",
        props: {
            age: {
                type: Number,
                // required: true,
                // default: 20

                validator(value) {
                    return value < 30
                }
            },

            caravab: {
                type: String,
                required: true
            }
        },

        emits: ['age-change'],
        methods: {
            onClickAge () {
                this.$emit('age-change', 3)
            }
        },
        computed: {
            ageDoubled () {
                return this.age * 2
            }
        }
    }
</script>