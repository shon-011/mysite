<template lang="pug">
  div.headercomponents(:class="colorMode")
    div.name shon.dev
    div.sidemenu
      div.content.-who
        nuxt-link(to="/me") who
      div.content.-works
        nuxt-link(to="/me") works
      div.content.-colormode(@click="changeColorMode") O

</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data() {
    return {}
  },
  computed: {
    colorMode() {
      return `-${this.$colorMode.value}`
    },
  },
  methods: {
    changeColorMode() {
      const mode = this.$colorMode
      mode.preference = mode.value === 'dark' ? 'light' : 'dark'
    },
  },
})
</script>
<style scoped lang="sass">
.headercomponents
  display: flex
  justify-content: space-evenly
  min-height: 50px
  align-items: center
  background-color: $header-bg-color-dark
  &.-light
    background-color: $header-bg-color-light
    color: $font-color-dark
  & > .sidemenu
    display: flex
    & > .content
      margin: 0 20px
      &.-colormode
        cursor: pointer
</style>
