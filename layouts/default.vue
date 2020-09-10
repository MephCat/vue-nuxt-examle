<template>
  <div>
    <Navbar/>

    <main>
      <div class="container">
        <nuxt/>
      </div>
    </main>
  </div>
</template>

<script>
import {Navbar} from "~/.nuxt/components";

export default {
  data () {
    return {
      Navbar
    }
  },
}
</script>
