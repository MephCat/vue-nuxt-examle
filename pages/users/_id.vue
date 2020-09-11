<template>
  <section>
    <h1>
      {{user.name}}
    </h1>
    <h3>
      Email : {{user.email}}
    </h3>

  </section>
</template>

<script>
export default {
  head(){
    return {
      titleTemplate: "%s - " + this.user.name,
      meta: [
        {
          name: 'description',
          content: this.user.name
        },
        {
          property: 'og:title',
          content: this.user.name
        },
        {
          property: 'og:locale',
          content: 'ru_RU'
        },
        {
          property: 'og:description',
          content: 'Пользователь'
        },
        {
          property: 'og:url',
          content: 'тут впихнуьб урл'
        },
        {
          property: 'og:site_name',
          content: 'тут название сайта'
        },
        {
          property: 'og:image',
          content: 'url для картинки'
        }
      ]
    }
  },
  validate({params}) {
    return /^\d+$/.test(params.id)
  },
  async asyncData({$axios, params}){
    const user = await $axios.$get('https://jsonplaceholder.typicode.com/users/' + params.id)
    return {user}
  }
}
</script>
