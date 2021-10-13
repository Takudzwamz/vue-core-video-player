<template>
  <!--<div class="movie-recommended" @click="changeMovie">
    <div class="cover">
      <img :src="item.cover2" alt="cover" />
      
      <div class="date">{{item.date}}</div>
    </div>
    <div class="detail">
      <div class="title">{{item.title}}</div>
      <div class="author">{{item.author}}</div>
      <div class="duration">Time: {{item.duration}}</div>
    </div>
  </div>-->

  <SkeletonScaffold
    @click="changeMovie"
    class="glass"
    borderRadius="10px"
    padding=" 2rem "
    primary="#90A79EA4"
    animDisable
  >
    <div @click="changeMovie" v-mCardImg>
      <img :src="item.cover2" alt="cover" width="100%" />
    </div>
    <!-- Card Image -->
    <br />

    <div v-mSquare  class="card1">{{ item.date }}</div>
    <!-- Profile image -->
    <br />

    <div v-mBox v-mLight class="card2">{{ item.title }}</div>
    <!-- Heading -->
    <div v-mBox v-mDark class="card3">{{ item.author }}</div>
    <!-- Heading -->
    <div v-mBox class="card4">Time: {{ item.duration }}</div>
    <!-- Sub-Heading -->
  </SkeletonScaffold>
</template>

<script>
export default {
  props: {
    item: Object,
  },
  name: "Recommended",
  methods: {
    changeMovie() {
      if (location.search) {
        location.href = location.href.replace(
          /\?vid=([a-z]+)/,
          "?vid=" + this.item.id
        );
      } else {
        location.href = location.href + "?vid=" + this.item.id;
      }
    },
  },
};
</script>

<style>
.glass {
  margin-bottom: 2em;
  background: rgba(255, 255, 255, 0.1);

  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  border-radius: 10px;
  border: 1px solid rgba(255, 255, 255, 0.25);
}

.card1 {
  border-radius: 10%;
  color: white;
  height: 2em;
  text-align: center;
  background: rgba(255, 255, 255, 0.1);

  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  border: 1px solid rgba(255, 255, 255, 0.25);
}

.card2 {
  height: 2.1em;
  width: 100%;
  font-size: 30px;
  color: white;
  border-radius: 10px;
  text-align: center;
  background: rgba(255, 255, 255, 0.1);

  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  border: 1px solid rgba(255, 255, 255, 0.25);
}

.card3 {
  height: 1.5em;
  width: 100%;
  font-size: 15px;
  color: white;
  border-radius: 10px;
  text-align: center;
  background: rgba(255, 255, 255, 0.1);

  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  
  border: 1px solid rgba(255, 255, 255, 0.25);
}
.card4 {
  height: 1.4em;
  width: 100%;
  color: white;
  font-size: 15px;
  border-radius: 10px;
  text-align: center;
  background: rgba(255, 255, 255, 0.1);
 
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
 
  border: 1px solid rgba(255, 255, 255, 0.25);
}
@media only screen and (max-width: 768px) {
  /* For mobile phones: */
  [class*="col-"] {
    width: 100%;
  }
  .card1 {
    border-radius: 10%;
    color: white;
    height: 2em;
    text-align: center;
  }

  .card2 {
    height: 3em;
    width: 100%;
    font-size: 15px;
    color: white;
    border-radius: 10px;
    text-align: center;
    text-transform: capitalize;
    font-weight: bold;
  }

  .card3 {
    height: 1.5em;
    width: 100%;
    font-size: 15px;
    color: white;
    border-radius: 10px;
    text-align: center;
  }
  .card4 {
    height: 1.4em;
    width: 100%;
    color: white;
    font-size: 15px;
    border-radius: 10px;
    text-align: center;
  }
}


</style>

