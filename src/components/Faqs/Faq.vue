<template>

  <transition
    @appear="faqsAppear"
  >

  <div
    class="faq-box"
    @click="clickShowAnswer($event)"
  >

    <div
      class="faq-box__question"
    >
      <p :id="questionBox"><slot name="question"></slot></p>
      <div class="faq-box__icon">
        <svg class="faq-box__icon--arrow" :id="arrow" width="10" height="7" xmlns="http://www.w3.org/2000/svg">
          <path d="M1 .799l4 4 4-4" stroke="#F47B56" stroke-width="2" fill="none" fill-rule="evenodd"/>
        </svg>
      </div>
    </div>
    <span class="bottom"></span>

    <transition
      @enter="enterEl"
      @leave="leaveEl"
    >
      <div
        v-if="showAnswer"
        class="faq-box__answer"
      >
        <p><slot name="answer"></slot></p>
      </div>

    </transition>

  </div>
  </transition>
</template>

<script>
import { gsap } from 'gsap'
import anime from 'animejs/lib/anime.es.js'

export default {
  name: 'Faqs',
  props: {
    id: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      showAnswer: false,
      questionBox: 'questionBox' + this.id,
      arrow: 'arrow' + this.id
    }
  },
  methods: {
    clickShowAnswer (event) {
      this.showAnswer = !this.showAnswer
    },

    faqsAppear () {
      gsap.fromTo(
        '.' + 'faq-box',
        {
          x: 20,
          autoAlpha: 0
        },
        {
          ease: 'power3.out',
          x: 0,
          autoAlpha: 1,
          duration: 0.600,
          stagger: 0.2
        }
      )
    },

    enterEl (el, done) {
      anime({
        targets: '.box-logo',
        easing: 'easeOutQuint',
        translateX: -40,
        duration: 600
      })

      anime({
        targets: '#aSymbol',
        stroke: '#e5e5e5',
        strokeDashoffset: [anime.setDashoffset, 0],
        easing: 'easeOutQuint',
        duration: 1500
      })

      anime({
        targets: '#arrow' + this.id,
        rotate: 180,
        easing: 'easeOutQuint',
        duration: 600
      })

      gsap.to(
        '#' + this.questionBox,
        {
          fontWeight: '700',
          ease: 'power3.out',
          duration: 0.2
        }
      )

      const height = el.clientHeight
      gsap.fromTo(el,
        {
          height: 0,
          y: -height,
          margin: 0,

          autoAlpha: 0
        },
        {
          height: height,
          y: 0,
          autoAlpha: 1,
          'margin-top': 15,

          ease: 'power3.out',
          duration: 0.2
        }
      )
    },

    leaveEl (el, done) {
      anime({
        targets: '.box-logo',
        easing: 'easeOutQuint',
        translateX: 0,
        duration: 600
      })

      anime({
        targets: '#aSymbol',
        stroke: '#3E2928',
        strokeDashoffset: [anime.setDashoffset, 0],
        easing: 'easeOutQuint',
        duration: 1500
      })

      anime({
        targets: '#arrow' + this.id,
        rotate: 0,
        easing: 'easeOutQuint',
        duration: 600
      })

      gsap.to(
        '#' + this.questionBox,
        {
          fontWeight: '400',
          ease: 'power3.out',
          duration: 0.2
        }
      )

      const height = el.clientHeight
      gsap.fromTo(el,
        {
          height: height,
          y: 0,
          autoAlpha: 1
        },
        {
          height: 0,
          y: -height,

          autoAlpha: 0,
          'margin-top': 0,

          ease: 'power3.out',
          duration: 0.2
        }
      )
    }
  }
}
</script>

<style scoped>

</style>
