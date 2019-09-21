<template>
  <div>
    <header class="main-header">
      <nav>
        <div
          class="link"
          @click="scroll('home')"
        >
          Acceuil
        </div>
        <div
          class="link"
          @click="scroll('skills')"
        >
          Compétences
        </div>
        <div
          class="link"
          @click="scroll('partners')"
        >
          Partenaires
        </div>
        <div
          class="link"
          @click="scroll('contact')"
        >
          Contact
        </div>
      </nav>
    </header>
    <nuxt />
  </div>
</template>

<script>
export default {
  mounted () {
    window.addEventListener('scroll', this.headerColor)
  },
  destroyed () {
    window.removeEventListener('scroll', this.headerColor)
  },
  methods: {
    scroll (id) {
      document.querySelector(`#${id}`).scrollIntoView({
        behavior: 'smooth'
      })
    },
    headerColor () {
      const mainHeader = document.querySelector('.main-header')
      const YOffset = window.pageYOffset + mainHeader.offsetHeight

      const sectionsEl = ['home', 'skills', 'partners', 'contact'].map(id => document.querySelector(`#${id}`))

      for (const i in sectionsEl) {
        const section = sectionsEl[i]

        if (YOffset - mainHeader.offsetHeight > section.offsetTop) {
          mainHeader.style.backgroundColor = getComputedStyle(section).backgroundColor.replace(/rgb/i, 'rgba').replace(/\)/i, ', .7)')
        } else {
          mainHeader.style.backgroundColor = null
        }

        if (YOffset - mainHeader.offsetHeight / 2 <= section.offsetHeight + section.offsetTop) {
          mainHeader.style.color = getComputedStyle(section).color

          return
        }
      }
    }
  }
}
</script>

<style scoped>
  header {
    position: fixed;
    width: 100%;

    color: white;

    /* transition-property: color; */
    transition-duration: .3s;
    transition-timing-function: ease;

    z-index: 10;
  }
  nav {
    font-family: "Manjari";
    display: flex;
    justify-content: space-around;
    padding: 20px 10px;
    letter-spacing: 1px;
    font-size: 1.3em;
  }

  header nav .link {
    cursor: pointer;
  }
</style>
