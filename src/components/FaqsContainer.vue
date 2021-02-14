<template>
<div class="faqs-container">
  <LogoBox></LogoBox>
  <FaqsBox></FaqsBox>
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
