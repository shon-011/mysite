<template lang="pug">
  div.headercomponents(:class="colorMode")
    nuxt-link(to="/me").logo
      div.name shon.dev >
        span.block(:class="colorMode")
    div.sidemenu(:class="colorMode")
      div.content.-link
        nuxt-link(to="/who") Who
      div.content.-link
        nuxt-link(to="/woks") Works
      div.content.-link
        nuxt-link(to="/shop") Shop
      div.content.-colormode(@click="changeColorMode")
        div(v-if='$colorMode.value === "dark"')
          Sun
        div(v-else)
          Moon

</template>

<script lang="ts">
import Vue from 'vue'
import Moon from '@/assets/image/moon.svg'
import Sun from '@/assets/image/sun.svg'

export default Vue.extend({
  components: {
    Moon,
    Sun,
  },
  data() {
    return {}
  },
  computed: {
    colorMode() {
      return `-${this.$colorMode.value}`
    },
    isPage() {
      return this.$route.path === '/me' ? '-ispage' : ''
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
  & > .logo
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
      &.-link:hover
        background: $link-hover-color-light
      &.-colormode
        cursor: pointer
        width: 20px
    &.-dark
      & > .content
        &.-link:hover
          background: $link-hover-color-dark
</style>
