<template>
    <h1>{{ title }}</h1>
    <input type="text" ref="name"/>
    <button @click="handleClick">click me</button>
</template>

<!--
    ----- multiple component -----
    App.vue : root component

    App.vue 
        - Header.vue
        - Article.vue
            - Content.vue
            - Comments.vue
        - Footer.vue
-->

<script>
export default {
    name: 'App',
    data() {
        return {
            title: 'My First Vue App :)'
        }
    },
    methods: {
        handleClick() {
            //refs 는 DOM 에 접근하기 위한 것.
            //js 의 document.querySelector 과 비슷...?
            //Vue의 가장 중요한 목적 중 하나가 개발자가 DOM을 다루지 않게 하는 것.
            //자주 쓰지 않기를 권장한다고 함.
            console.log(this.$refs.name)
            this.$refs.name.classList.add('active')
            this.$refs.name.focus()
        }
    }
}
</script>

<style scoped>

</style>