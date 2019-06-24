<template lang="html">
  <div id="add-film">
    <h2>Add a New Film</h2>
    <form>
      <!-- <label>Film Title:</label> -->
      <input type="text" v-model="title" required>
      <p>{{title}}</p>


    </form>
    <div>
      <!-- <h3>Films Title:</h3> -->
    </div>
  </div>

</template>

<script>

export default {
  data(){
    return{
      title: ""
    }
  }
}
</script>

<style lang="css" scoped>
</style>
