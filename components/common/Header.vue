<template lang="pug">
  div.headercomponents(:class="colorMode")
    div.name shon.dev >
      span.block(:class="colorMode")
    div.sidemenu
      div.content.-who
        nuxt-link(to="/me") Who
      div.content.-works
        nuxt-link(to="/me") Works
      div.content.-colormode(@click="changeColorMode")
        MoonSun

</template>

<script lang="ts">
import Vue from 'vue'
import MoonSun from '@/assets/image/moon_sun.svg'

export default Vue.extend({
  components: {
    MoonSun,
  },
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
  font-family: monospace
  font-size: 15px
  font-weight: 500
  display: flex
  justify-content: space-evenly
  min-height: 50px
  align-items: center
  background-color: $header-bg-color-dark
  &.-light
    background-color: $header-bg-color-light
    color: $font-color-dark
  & > .name
    & > .block
      display: inline-block
      width: 10px
      height: 1px
      background: $cursor-color-dark
      margin-left: 5px
      animation: cursor 1.5s infinite
      &.-light
        background: $cursor-color-light
  & > .sidemenu
    display: flex
    & > .content
      margin: 0 20px
      &.-colormode
        cursor: pointer
        width: 20px
        & > img
          width: 100%
          height: auto
</style>
