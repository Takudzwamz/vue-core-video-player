<template>
  

  
  <SkeletonScaffold
    @click="changeMovie"
    class="glass"
    borderRadius="10px"
    padding=" 2rem "
    primary="#952DAFA4"
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
  name: 'MovieItem',
  methods: {
    changeMovie () {
      if (location.search) {
        location.href = location.href.replace(/\?vid=([a-z]+)/, '?vid=' + this.item.id)
      } else {
        location.href = location.href + '?vid=' + this.item.id
      }
    }
  },
}
</script>

<style>
  .movie-item {
    cursor: pointer;
    display: flex;
    margin-bottom: 20px;
  }
  .movie-item .cover {
    position: relative;
    width: 166px;
    overflow: hidden;
    background: #000;
  }
  .movie-item:hover .cover img {
    opacity: .7;
    transform: scale(1.25, 1.25);

  }
  .movie-item .cover img {
    width: 100%;
    transition: transform ease .25s;
  }
  .movie-item .cover .duration {
    position: absolute;
    right: 5px;
    bottom: 5px;
    padding: 3px 6px;
    line-height: 1.2em;
    background-color: rgba(0,0,0, .65);
    color: #fff;
    font-size: 12px;
    border-radius: 2px;
  }
   .movie-item .detail {
    padding-left: 10px;
    font-size: 14px;
    color: rgba(0,0,0, .45);
  }
  .movie-item .detail .title {
    color: #000;
    font-size: 16px;
  }
  .movie-item .detail .author{
    font-size: 13px;
    line-height: 1em;
  }
  .movie-item .detail .date {
    display: inline-block;
    padding: 3px 6px;
    line-height: 1em;
    background-color: #31C2F2;
    color: #fff;
    font-size: 12px;
    border-radius: 2px;
  }
  .movie-item .detail .data.hot {
    background-color: #ff6060;
  }

</style>

