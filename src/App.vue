
<template>
  <div>
    <h1>Studio Ghibli Films</h1>

    <div class="main-container">
      <div class="">
        <img width="500px" v-for="image in images" :src="image"/>
      </div>


      <add-film :title='title'></add-film>
      <film-list :films='films'></film-list>
      <film-detail :film="selectedFilm"></film-detail>

    </div>

  </div>
</template>

<script>
import { eventBus } from './main.js'
import FilmList from './components/FilmList.vue';
import FilmDetail from './components/FilmDetail.vue';
import AddFilm from './components/AddFilm.vue';

export default {
  name: 'app',
data(){
  return {
    images: ['https://www.saga.co.uk/contentlibrary/saga/publishing/verticals/entertainment/films-and-tv/films_tv-hero-1260x600.jpg',
       'https://cdn0.tnwcdn.com/wp-content/blogs.dir/1/files/2012/06/10525562_web.jpg'],
    title: "",
    films: [],
    selectedFilm: null
  }




},

mounted() {
  fetch('https://ghibliapi.herokuapp.com/films')
  .then(res => res.json())
  .then(films => this.films = films)
  eventBus.$on('film-selected', (film) => {
    this.selectedFilm = film;
  })

},

components: {
  "film-list": FilmList,
  "film-detail": FilmDetail,
  "add-film": AddFilm


}
}
</script>

<style>
#add-film *{
  box-sizing:border-box;
  display: flex;
}



input[type="text"].textrea{
  display: flex;
  width: 100%;
  padding: 8px;
}
body {
  background-image: linear-gradient(to top, #8a45b8 10%, #bac4e0 100%);

}

h1 {
  text-align: center;
  color: red;
  font-family: fantasy;
  font-weight: bolder;
  background-color: lightpink;
}
h2 {
  text-align: center;
  display: flex;
  color: darkgreen;
  font-family: cursive;
  font-weight: bolder;

}

.main-container {
  display: flex;
  justify-content: space-between;
  width: 80%;
  margin: 10px;
}


</style>








    <!-- </div>
<div class="">
  <img width="1000px" v-for="image in images" :src="image"/>
</div>
  </div>
</template>

<script> --> */




/* <!-- // export default {
//   name: 'app',
// data(){
//   return {
//     images: [//'https://www.saga.co.uk/contentlibrary/saga/publishing/verticals/entertainment/films-and-tv/films_tv-hero-1260x600.jpg',
//   'https://cdn0.tnwcdn.com/wp-content/blogs.dir/1/files/2012/06/10525562_web.jpg'],
//     films: [],
//     favourites: []
//   }


}, --> */
