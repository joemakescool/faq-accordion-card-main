<template>
<div class="faqs-container">
  <div class="left-side">
    <LogoBox></LogoBox>
  </div>

  <div class="right-side">
    <FaqsBox></FaqsBox>
  </div>
</div>
</template>

<script>
import FaqsBox from '@/components/Faqs/FaqsBox'
import LogoBox from '@/components/LogoBox'

export default {
  name: 'FaqsContainer',
  components: {
    FaqsBox, LogoBox
  }
}
</script>

<style scoped>

</style>
