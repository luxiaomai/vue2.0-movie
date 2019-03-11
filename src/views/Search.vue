// 搜索页
<template>
  <div>
    <movie-list :movie-type="movieType" ref="updateList"></movie-list>
  </div>
</template>

<script>
  import movieList from '@/components/MovieList.vue'
  export default {
    data(){
      return {
        movieType: 'search'
      }
    },
    watch: {
      //监听路由，搜索页重复的时候改变路由状态，页面重新加载
      '$route'(to, from) {
        //防止返回重复调用
        if (to.path.indexOf('/search/') == 0) {
          //调用子组件
          this.$refs.updateList.loadMovieList();
        }
      }
    },
    components: {
      'movie-list': movieList
    }
  }
</script>
<style>
</style>
