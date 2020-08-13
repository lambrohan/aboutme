<template>
  <div id="app-footer">
    <a class="git" target="_blank" href="https://www.github.com/lambrohan">
      <img src="~/static/github.png" />
      Github
    </a>
    <div class="nuxt">
      Built with <a target="_blank" href="https://www.nuxtjs.org">Nuxt</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppFooter',
}
</script>

<style lang="scss" scopped>
#app-footer {
  width: 100%;
  position: relative;
  min-height: 45px;
  background: #f5f5f5;
  display: flex;
  align-items: center;
  justify-content: flex-end;
  padding: 0 32px;
  a {
    text-decoration: none;
    color: inherit;
    font-weight: 300;
    margin: 0;
    padding: 0;
  }
  .git {
    display: flex;
    align-items: center;
    img {
      width: 25px;
      margin-right: 8px;
    }
  }

  .nuxt {
    position: relative;
    font-weight: 300;
    margin-left: 32px;

    a {
      font-weight: 500;
    }
  }
}
</style>
