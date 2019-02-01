<template lang="pug">
  q-page.page-index.flex.flex-center.column
    div.page-index__overlay
    h1.page-index__title Thiago Moreira
    p.page-index__text Coming Soon
    div.page-index__buttons.flex
      q-btn(@click="redirectTo('github.com/thiagocmoreira')", icon="mdi-github-circle" color="grey-2" flat round)
      q-btn(@click="redirectTo('gitlab.com/thiagocmoreira')", icon="mdi-gitlab" color="orange-8" flat round)
      q-btn(@click="redirectTo('linkedin.com/in/thiagocmoreira')" ,icon="mdi-linkedin-box" color="blue-6" flat round)
</template>

<script>
export default {
  name: 'PageIndex',
  methods: {
    redirectTo (link) {
      window.open(`https://www.${link}`, '_blank')
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~variables'
.page-index
  background radial-gradient(#333, $grey-10)
  color white

  &__overlay
    pointer-events none
    position absolute
    width 100%
    height 100%
    background repeating-linear-gradient(180deg, rgba(0, 0, 0, 0) 0, rgba(0, 0, 0, 0.3) 50%, rgba(0, 0, 0, 0) 100%)
    background-size auto 4px
    z-index: 99
    opacity: 0.3

    &::before
      content ''
      pointer-events none
      position absolute
      display block
      top 0
      left 0
      right 0
      bottom 0
      width 100%
      height 100%
      background-image linear-gradient(0deg, transparent 0%, rgba(99, 99, 99, 0.2) 2%, rgba(99, 99, 99, 0.8) 3%, rgba(99, 99, 99, 0.2) 3%, transparent 100%)
      background-repeat no-repeat
      animation scan 7.5s linear 0s infinite

  &__title
    font-size 42px
    margin 0 0 15px 0
    font-weight 500
    text-align center
    @media(max-width: 735px)
      font-size 36px
    @media(max-width: 630px)
      font-size 28px
    @media(max-width: 414px)
      padding 0 25px
      font-size 22px

  &__text
    text-align center
    font-size 24px
    margin 0 0 30px 0
    @media(max-width: 630px)
      font-size 20px
      margin 0 0 20px 0
    @media(max-width: 414px)
      margin 0 0 15px 0
      font-size 19px

  &__buttons
    .q-btn
      margin 0 5px
      font-size 22px
      padding 0
      @media(max-width: 630px)
        font-size 20px
      @media(max-width: 414px)
        font-size 18px

  @keyframes scan {
    0%        { background-position: 0 -100vh }
    35%, 100% { background-position: 0 100vh }
  }
</style>
