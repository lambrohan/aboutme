<template>
  <div id="showcase">
    <div class="left">
      <img :src="currentProject.img" />
      <img :src="currentProject.img2" />
    </div>
    <div class="right">
      <h4>{{ currentProject.title }}</h4>
      <p>{{ currentProject.p1 }}</p>
      <p v-if="currentProject.p2">{{ currentProject.p2 }}</p>
      <div class="navigation">
        <img
          src="/left_arr.svg"
          @click="
            currentProjectIndex > 0
              ? currentProjectIndex--
              : (currentProjectIndex = projects.length - 1)
          "
        />
        <span></span>
        <img
          src="/rit_arr.svg"
          @click="
            currentProjectIndex < projects.length - 1
              ? currentProjectIndex++
              : (currentProjectIndex = 0)
          "
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectShowcase',
  data() {
    return {
      currentProjectIndex: 0,
      projects: [
        {
          img: '/kajave.jpg',
          img2: '/kajave2.jpg',
          title: 'Portfolio Site',
          p1: `I built this site for a local furniture store using Vue and Firebase. This site gets product data from Firebase Firestore using web SDK’s & then display them on pages. I’ve also used Vuex in  this site to save and fetch products & global state variables such as scroll position, element states etc`,
          p2: `I also did all the styling for this project from scratch & using SCSS as preprocessor.`,
        },
        {
          img: '/juvel.jpg',
          img2: '/juvel2.jpg',
          title: 'E-Commerce Site',
          p1: `At formecmedia where I work as full stack dev, we have a e-commerce project for a big jewellery brand. I am the lone developer working on it & also responsible for deployment. This project is being built using Nuxt and Strapi CMS. We create design mockups using Figma & then its my job to convert each page/element to functional vue components.`,
          p2: `In backend stack I used MongoDB with Strapi to build API's & GraphQL endpoints as well. In frontend I used @nuxtjs/apollo module to consume the graphql api's. Used Vuex to implement Cart, Wishlist features.`,
        },
        {
          img: '/formec.jpg',
          img2: '/formec2.jpg',
          title: 'Media Agency Site',
          p1: `As always I used Nuxt to create this static site. This site changes the colors for font & backgrounds which is achieved usig Vuex store and dynamic css variables.`,
          p2: `Many components were designed in such a way that they can be user on different pages with different information.`,
        },
      ],
    }
  },
  computed: {
    currentProject: function () {
      return this.projects[this.currentProjectIndex]
    },
  },
}
</script>

<style lang="scss" scopped>
#showcase {
  width: 100%;
  min-height: 100vh;
  max-height: 100vh;
  background: $primary;
  display: flex;
  align-items: stretch;
  padding: 48px;

  @include for-phone-only {
    flex-direction: column;
    padding: 1.4em;
    flex-direction: column-reverse;
  }

  .left {
    width: 45%;
    position: relative;

    @include for-phone-only {
      width: 100%;
    }
    img {
      width: 100%;
      margin-top: 12px;
    }
  }

  .right {
    width: 55%;
    position: relative;
    padding-left: 80px;
    color: white;

    @include for-phone-only {
      width: 100%;
      padding: 0;
      max-height: 400px;
      overflow-y: scroll;
    }

    .navigation {
      display: flex;
      align-items: center;
      justify-content: space-between;
      max-width: 120px;
      min-width: 120px;
      background: #000;
      padding: 12px;
      border-radius: 4px;
      position: absolute;
      right: 0;
      bottom: 0;
      transition: 0.3s ease all;

      @include for-phone-only {
        opacity: 0.4;
      }

      span {
        width: 8px;
        height: 8px;
        background: #fff;
        border-radius: 50%;
      }

      img {
        opacity: 0.7;
        transition: 0.3s ease all;
        &:hover {
          opacity: 1;
          cursor: pointer;
        }

        &:active {
          transform: scale(0.9);
        }
      }
    }

    h4 {
      font-weight: 500;
      font-size: 48px;
      line-height: 57px;
      /* identical to box height */

      color: #c8c8c8;
      margin-bottom: 0.8em;

      @include for-phone-only {
        margin-top: 0.8em;
      }
    }

    p {
      font-style: normal;
      font-weight: 300;
      font-size: 24px;
      line-height: 32px;
      color: #d2d2d2;
      margin-bottom: 1em;
    }
  }
}
</style>
