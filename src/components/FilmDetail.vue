
<template lang="html">
  <div v-if="film">
    <h3>{{film.title}}</h3>
    <p>Director: {{film.director}}</p>
    <p>Producer: {{film.producer}}</p>
    <p>Release_date: {{film.release_date}}</p>
    <p>Rt_score: {{film.rt_score}}</p>

    <p>Description: {{film.description}}</p>



  </div>

</template>

<script>
export default {
  name: 'film-detail',
  props: ['film']
}
</script>
