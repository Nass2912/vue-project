<template>
    <button type="button" @click="onClickAge">increment</button>

    <p>The user is {{ age }} years old and drives {{ caravab }} From user.vue</p>

    <p> {{ ageDoubled }}</p>
</template>

<script>
export default {
    name: "User",
    props: ["age", "caravab"],
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