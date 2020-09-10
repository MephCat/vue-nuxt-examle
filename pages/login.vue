<template>
  <section>
    <form @submit.prevent="onSubmit">
      <h1>
        Login page
      </h1>
      <div class="form-group">
        <input type="text"
               class="form-control">
      </div>
      <NuxtLink to="/" >
        To Home-page
      </NuxtLink>
      <button class="btn btn-primary"
              type="submit">
        login
      </button>
    </form>
  </section>
</template>
<style scoped>
form{
  width: 500px;
  margin: 0 auto;
}
</style>

<script>
export default {
  layout:'empty',
  methods: {
    onSubmit(){
      this.$store.dispatch('login')
      this.$router.push('/')
    }
  }
}
</script>
