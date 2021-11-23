<template lang="pug">
div.section
  div.title shon.dev
  div.self
    div.top
      div.icon
        img.img(src="@/assets/image/icon.jpg")
      div.name Shona Tanaka
        div.age 1998.01.11 23 y.o.
      div.comment
        | I am a software developer, working as a full-time employee at enJapan Inc.
        br
        |  My favorite framework is Nuxt.js.


</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>
<style scoped lang="sass">
.section
  margin: 0 6%
  & > .title
    font-size: 50px
    text-align: center
    font-weight: 500
    margin: 5% auto
  & > .self
    & > .top
      margin: 0 auto
      text-align: center
      & > .icon
        margin: 0 auto
        height: auto
        width: 20%
        @media ($pc)
          width: 10%
        & > img
          object-fit: cover
          width: 100%
          height: 100%
          border-radius: 50%
      & > .name
        font-size: 20px
        margin: 30px auto
      & > .comment
        line-height: 35px
        @media ($pc)
          line-height: 25px
</style>
