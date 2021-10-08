<template>
  <b-container class="bv-example-row main">
    <b-row>
      <b-col cols="12">
        <div id="vue-core-video-player-box" class="">
          <vue-core-video-player style=" background: white;" :cover="currentMovie.cover3"  :src="currentMovie.source"></vue-core-video-player>
        </div>
        <div class="movie-detail">
          <h1 class="title">{{currentMovie.title}}</h1>
          <div class="date">{{currentMovie.author}} - {{currentMovie.date}}</div>
          <div class="desc">{{currentMovie.desc}} </div>
          <div class="btn-wrap">
            <b-button variant="outline-success" href="https://registertovotezw.live" >
              
              Go back to Register to vote page
            </b-button>
          </div>
          
        </div>
        <div class="recommend-list">
          <RecommendedItem v-for="movie in recommendList" :key="movie.cover" :item="movie"></RecommendedItem>
        </div> 
        <!---->
        <div class="thanks">
          ❤ Lets all register to vote Zimboz
        </div>
      </b-col>
      <b-col cols="8" class="play-list">
        <h2>Play List</h2>
        <MovieItem v-for="movie in movieList" :key="movie.cover" :item="movie"></MovieItem>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>

import MovieItem from './MovieItem.vue'
import RecommendedItem from './Recommended.vue'
import DATA from '../assets/data'

let movie = DATA[2]

if (location.search) {
  var vid = location.search.split('=')[1]
  DATA.forEach(item => {
    if (item.id === vid) {
      movie = item
    }
  })
}


export default {
  name: 'Main',
  components: {
    MovieItem,
    RecommendedItem
  },
  data() {
    return {
      title: '',
      movieList: DATA,
      recommendList: [ DATA[4], DATA[1], DATA[0]],
      currentMovie: movie
    }
  },
  methods: {
    open() {
      window.open('https://registertovotezw.live/')
    }
  },
}
</script>

<style>

.vue-core-video-player-control.timespan {
    line-height: 74px;
    width: 100%;
    color:white;
    font-family: Arial!important;
}
  .example-player {
    position: relative;
    
    height: 610px;
    background-color: #000;
    font-weight: normal; 
  }

  
@media only screen and (max-width: 768px) {
  /* For mobile phones: */
  [class*="col-"] {
    width: 100%;
  }
.example-player{
  height: 200px;
}

}


  .movie-detail{
    padding-top: 20px;
    color: rgba(0,0,0, .65);
  }
  .movie-detail h1{
    font-size: 20px;
    color: #000;
  }
  .movie-detail .date {
    font-size: 14px;
  }
  .movie-detail .desc {
    font-size: 13px;
    padding: 10px 20px 10px 0;
  }
  .movie-detail .btn-wrap {
    padding-right: 20px;
    text-align: right;
  }
  .play-list h2 {
    font-size: 18px;
    color: rgba(0,0,0, .85);
    padding-bottom: 10px;
  }
  .recommend-list {
    margin-top: 40px;
    padding-top: 40px;
    width: 100%;
    padding-bottom: 40px;
    border-top: 1px solid #ddd;
  }
  .thanks {
    padding: 20px 0 40px;
    color: rgba(0, 0, 0, .25);
    font-size: 13px;
    text-align: center;
  }
  .recommend-list:after{
    content: '';
    display: block;
    clear: both;
  }
</style>
