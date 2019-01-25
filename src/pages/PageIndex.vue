<template lang="pug">
  q-page.page-index.flex.flex-center.column
    h1.page-index__title Thiago Moreira - Personal Website
    p.page-index__text Coming Soon
    div.page-index__buttons.flex
      q-btn(@click="redirectTo('github.com/thiagocmoreira')", icon="mdi-github-circle" color="grey-1" flat round)
      q-btn(@click="redirectTo('gitlab.com/thiagocmoreira')", icon="mdi-gitlab" color="grey-1" flat round)
      q-btn(@click="redirectTo('linkedin.com/in/thiagocmoreira')" ,icon="mdi-linkedin-box" color="grey-1" flat round)
      q-btn(@click="redirectTo('instagram.com/thiagueeras')" icon="mdi-instagram" color="grey-1" flat round)
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
  background $grey-10
  color white

  &__title
    font-size 42px
    margin 0 0 30px 0
    font-weight 500
    text-align center
    @media(max-width: 735px)
      font-size 36px
    @media(max-width: 630px)
      font-size 28px
      margin 0 0 20px 0
    @media(max-width: 414px)
      padding 0 25px
      font-size 22px
      margin 0 0 15px 0

  &__text
    text-align center
    font-size 28px
    margin 0 0 30px 0
    @media(max-width: 630px)
      font-size 22px
      margin 0 0 20px 0
    @media(max-width: 414px)
      margin 0 0 15px 0
      font-size 19px

  &__buttons
    .q-btn
      margin 0 5px
      font-size 26px
      padding 0
      @media(max-width: 630px)
        font-size 20px
      @media(max-width: 414px)
        font-size 18px
</style>
