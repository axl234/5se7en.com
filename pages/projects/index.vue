<template>
  <section class="articleList">
    <ul>
    	<li v-for="item in articleList">{{ item.title }}</li>
    </ul>
  </section>
</template>

<script>
import axios from 'axios';

export default {
  async asyncData ({ params }) {
    let { data } = await axios.get(`/api/fortuneChur/hot/latest.html`)
    return { articleList: data }
  }
}  
</script>

<style lang="scss" scoped>
.articleList{
  padding: 50px;
  @media (max-width: 991px) {
    padding-left: 0;
    padding-right: 0;
  }
  ul{
    li{
	  width: 600px;
	  margin: 0 auto;
	  text-align: center;
	  height: 50px;
	  line-height: 50px;
	  border-bottom: 1px solid #ccc;
	  @media (max-width: 991px) {
	  	width: 100%;
	  	font-size: 14px;
	  }
	}
  }
}
</style>
