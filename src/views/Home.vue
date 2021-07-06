<template>
  <div class="field is-flex is-justify-content-end">
    <input
      id="switchRtlExample"
      type="checkbox"
      name="switchRtlExample"
      class="switch is-rtl"
      checked="dark"
      @click="toggleMode"
    />
    <label for="switchRtlExample" v-if="dark"> Dark Mode </label>
    <label for="switchRtlExample" v-else> Light Mode </label>
  </div>

  <section class="section" :class="{ 'has-background-dark': dark }">
    <div class="columns is-touch is-multiline">
      <div class="column is-2">
        <SideNav />
      </div>
      <div class="column">
        <img alt="Vue logo" src="../assets/logo.png" />
        <Nav />
        <HelloWorld msg="Welcome to Your Vue.js App" />
      </div>
    </div>
  </section>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Nav from '@/components/Nav.vue'
import SideNav from '@/components/SideNav.vue'
import { ref } from 'vue'

export default {
  name: 'Home',
  components: {
    HelloWorld,
    Nav,
    SideNav
  },
  setup() {
    const dark = ref(null)
    dark.value = true
    const toggleMode = () => {
      dark.value = !dark.value
    }
    return {
      dark,
      toggleMode,
    }
  },
}

</script>
