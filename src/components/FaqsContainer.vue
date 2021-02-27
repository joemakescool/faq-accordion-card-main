<template>
<div class="faqs-container">
  <transition @appear="leftSideAppear">
    <div class="left-side">
      <LogoBox></LogoBox>
    </div>
  </transition>

  <div class="right-side">
    <FaqsBox></FaqsBox>
  </div>
</div>
</template>

<script>
import FaqsBox from '@/components/Faqs/FaqsBox'
import LogoBox from '@/components/LogoBox'
import anime from 'animejs'

export default {
  name: 'FaqsContainer',
  components: {
    FaqsBox, LogoBox
  },
  methods: {
    leftSideAppear () {
      anime({
        targets: '.left-side',
        translateX: [-30, 0],
        opacity: [0, 1],
        easing: 'easeOutQuint',
        delay: anime.stagger(100),
        duration: 600
      })
    }
  }
}
</script>

<style scoped>

</style>
