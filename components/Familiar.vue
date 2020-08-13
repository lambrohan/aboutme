<template>
  <div id="familier">
    <h4>I'm super familiar with</h4>
    <div class="icons">
      <img
        v-for="item in icons"
        :key="item.icon"
        :src="item.icon"
        :title="item.title"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'FamilierComp',
  data() {
    return {
      icons: [
        {
          icon: '/git.png',
          title: 'Git',
        },
        {
          icon: '/vsc.png',
          title: 'VS Code',
        },
        {
          icon: '/postman.png',
          title: 'Postman',
        },
        {
          icon: '/strapi.png',
          title: 'Strapi- Headless CMS',
        },
        {
          icon: '/gql.png',
          title: 'GraphQL',
        },
        {
          icon: '/apollo.png',
          title: 'Apollo',
        },
        {
          icon: '/figma.svg',
          title: 'Figma',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scopped>
#familier {
  width: 100%;
  position: relative;
  min-height: 350px;
  padding: 48px 0;

  h4 {
    text-align: center;
    font-weight: normal;
    font-size: 2em;
  }

  .icons {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 48px;
    flex-wrap: wrap;
    img {
      max-height: 50px;
      margin: 0 32px;

      @include for-phone-only {
        margin: 24px;
        max-height: 30px;
      }

      @include for-tablet-only {
        margin: 32px;
      }
    }
  }
}
</style>
