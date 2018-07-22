<template>
  <div id="app">
    <ImageEffects/>
  </div>
</template>

<script>
import ImageEffects from './components/ImageEffects'

export default {
  name: 'App',
  components: {
    ImageEffects
  }
}
</script>

<style>
:root {
      --base: #ffc600;
      --spacing: 10px;
      --blur: 10px;
    }

    img {
      padding: var(--spacing);
      background: var(--base);
      filter: blur(var(--blur));
    }

    .hl {
      color: var(--base);
    }

    /*
      misc styles, nothing to do with CSS variables
    */

    body {
      text-align: center;
    }

    body {
      background: #193549;
      color: white;
      font-family: 'helvetica neue', sans-serif;
      font-weight: 100;
      font-size: 50px;
    }
</style>
