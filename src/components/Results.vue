<template>
  <div>
    <h1>your click speed: {{resu}} ms</h1>
    <p v-if="resu < 200">wow! so fast. I can't even see it 🧐</p>
    <p v-else-if="resu < 400 "> woah fast, still not enough bruh! 🤨</p>
    <p v-else>wow! still average 🤓</p>
  </div>
</template>

<script>
export default {
    name: 'Results',
    props: {
      resu: Number
    },
    methods: {

    }
}
</script>

<style>

</style>