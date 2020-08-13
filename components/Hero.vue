<template>
  <div id="hero">
    <a class="git" target="_blank" href="https://www.github.com/lambrohan"
      ><img src="github.png" />Github</a
    >
    <h2>Hello.</h2>
    <h4>My name is Rohan Lamb.</h4>
    <p>
      I am a Full Stack Developer. I love to build fast & beautifull user
      experience for mobile & web. I know Nuxt, NodeJS &amp; Native Android
      Developement. I have been building apps with above stack for more than 3
      years. I am self taught developer & a Mechanical Engineer. Sometimes I
      write articles about programming on my medium blog
      <a class="medium" href="https://medium.com/@lambrohan" target="_blank"
        >here </a
      >.
    </p>
    <br />
    <p>
      Apart from programming, I enjoy listening to classical & electronic music.
      <a class="medium" href="mailto:lambrohan@gmail.com">Contact</a> want to
      have a nerdy conversation!
    </p>
  </div>
</template>

<script>
export default {
  name: 'HeroComponent',
}
</script>

<style lang="scss" scopped>
#hero {
  width: 100%;
  position: relative;
  min-height: 98vh;
  padding: 16px 2em;

  @include for-tablet-portrait-up {
    padding: 2em 8em;
  }

  .medium {
    text-decoration: none;
    position: relative;
    padding: 0;
    margin: 0;
    overflow: hidden;
    color: inherit;
    &::after {
      content: '';
      z-index: -1;
      position: absolute;
      left: 0;
      bottom: -1px;
      width: 100%;
      height: 6px;
      background: rgb(140, 147, 255);
      transition: 0.3s ease all;
    }

    &:hover {
      &::after {
        height: 12px;
      }
    }
  }

  .git {
    position: absolute;
    display: flex;
    align-items: center;
    font-weight: normal;
    right: 32px;
    padding: 6px 24px;
    text-decoration: none;
    color: inherit;
    border-radius: 48px;
    cursor: pointer;
    border: 0.5px solid rgba(0, 0, 0, 0.137);
    img {
      width: 25px;
      margin-right: 8px;
    }
  }

  h2 {
    font-size: 4.5em;
    margin: 0.5em 0;

    @include for-phone-only {
      margin-top: 1.4em;
    }
  }

  h4 {
    font-weight: 500;
    font-size: 1.5em;
    margin-bottom: 2em;
  }

  p {
    font-style: normal;
    font-weight: 300;
    font-size: 1.5em;
    color: #424242;
    line-height: 1.5em;
    @include for-tablet-landscape-up {
      max-width: 65%;
    }
  }
}
</style>
