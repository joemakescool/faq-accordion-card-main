<template>

  <div class="faqs-box">
    <h1 class="faqs-box__title">FAQ</h1>

  <Faq id="faq1">
    <template v-slot:question>
      How many team members can I invite?
    </template>

    <template v-slot:answer>
      You can invite up to 2 additional users on the Free plan. There is no limit on
      team members for the Premium plan.
    </template>
  </Faq>
    <div class="faq-box__divider">

    </div>

  <Faq id="faq2">
    <template v-slot:question>
      What is the maximum file upload size?
    </template>

    <template v-slot:answer>
      No more than 2GB. All files in your account must fit your allotted storage space.
    </template>
  </Faq>

    <div class="faq-box__divider">

    </div>

  <Faq id="faq3">
    <template v-slot:question>
      How do I reset my password?
    </template>

    <template v-slot:answer>
      Click “Forgot password” from the login page or “Change password” from your profile page.
      A reset link will be emailed to you.
    </template>
  </Faq>

    <div class="faq-box__divider">

    </div>

  <Faq id="faq4">
    <template v-slot:question>
      Can I cancel my subscription?
    </template>

    <template v-slot:answer>
      Yes! Send us a message and we’ll process your request no questions asked.
    </template>
  </Faq>

    <div class="faq-box__divider">

    </div>

  <Faq id="faq5">
    <template v-slot:question>
      Do you provide additional support?
    </template>

    <template v-slot:answer>
      Chat and email support is available 24/7. Phone lines are open during normal business hours.
    </template>
  </Faq>

    <div class="faq-box__divider">

    </div>
  </div>
</template>

<script>
import Faq from '@/components/Faqs/Faq'

export default {
  name: 'FaqsBox',
  components: {
    Faq
  }
}
</script>

<style scoped>

</style>
