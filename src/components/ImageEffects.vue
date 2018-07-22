<template>
  <div class="hello">
    <h2>Update CSS Variables with <span class='hl' :style="hl">JS</span></h2>

    <div class="controls">
      <label for="spacing">Spacing:</label>
      <input type="range" name="spacing" @change="handleUpdate('spaceing')" min="10" max="200" v-model="spacing">

      <label for="blur">Blur:</label>
      <input type="range" name="blur" @change="handleUpdate('blur')"  min="0" max="25" v-model="blur">

      <label for="base">Base Color</label>
      <input type="color" name="base" @change="handleUpdate('base')"  v-model="baseColor" >
    </div>

    <img src="https://source.unsplash.com/7bwQXzbF6KE/800x500" 
    :style="img">
  </div>
</template>

<script>
export default {
  name: 'ImageEffects',
  computed: {
    img () {
      return {
        padding: `${this.spacing}px`,
        background: this.baseColor,
        filter: "blur(" + `${this.blur}px` + ")",
      };
    },
    hl () {
      return {color: this.baseColor};
    },
  },
  data () {
    return {
      baseColor: "#ffc600",
      spacing: 10,
      blur: 10,
    }
  },
  methods: {
    handleUpdate(name) {
      // const suffix = this.dataset.sizing || '';
      console.log('changed')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .controls {
      margin-bottom: 50px;
    }

    a {
      color: var(--base);
      text-decoration: none;
    }

    input {
      width:100px;
    }

    img {
      padding: var(--spacing);
      background: var(--base);
      filter: blur(var(--blur));
    }

    .hl {
      color: var(--base);
    }
</style>
