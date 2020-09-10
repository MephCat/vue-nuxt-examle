<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <NuxtLink to="/" class="navbar-brand">
      Nuxt JS
    </NuxtLink>

    <div class="collapse navbar-collapse">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item">
          <NuxtLink exact
                     no-prefetch
                     active-class="active"
                     to="/"
                     class="nav-link">
            Home
          </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink active-class="active"
                     no-prefetch
                     to="/about"
                     class="nav-link">
            About
          </NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink active-class="active"
                     no-prefetch
                     to="/users"
                     class="nav-link">
            Users
          </NuxtLink>
        </li>
        <li class="nav-item" v-if="!hasToken">
          <NuxtLink
              to="/login"
             class="nav-link">
            login
          </NuxtLink>
        </li>
        <li class="nav-item" v-else>
          <a href="#"
             class="nav-link"
             @click.prevent="logout">
            logout
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>
<script>
export default {
  computed: {
    hasToken(){
      return this.$store.getters.hasToken
    }
  },
  methods: {
    logout(){
      this.$store.dispatch('logout')
      this.$router.push('/login')
    }
  }
}
</script>
