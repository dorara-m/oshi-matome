<template>
  <div class="detail">
    <div class="head">
      <h1>{{cmsData.title}}</h1>
      <p>nekomata okayu</p>
      <img src="" alt="">
    </div>
    <div class="points">
      <a href="http://" target="_blank" rel="noopener noreferrer">公式プロフィール</a>
      <p>推し歴：1000日</p>
      <div class="stars">
        <div class="stars_item">声の良さ：★★★★★</div>
        <div class="stars_item">平和な言葉遣い：★★★★★</div>
        <div class="stars_item">ボクっ娘：★★★★★</div>
      </div>
    </div>
    <div class="richArea"></div>
    <div class="movieArea">
      <div class="title">オススメ動画</div>
      <ul>
        <li>動画サムネつき1</li>
        <li>動画サムネつき2</li>
        <li>動画サムネつき3</li>
      </ul>
    </div>
  </div>
</template>


<script setup>
import axios from 'axios'
let cmsData = ref({})
const route = useRoute()

axios.get(`https://uma-chat.microcms.io/api/v1/blog/${route.params.id}`, {
  headers: { 'X-MICROCMS-API-KEY': 'eb94b33042b64da7badbbba4642b22db81a3' }
})
  .then((response) => {
    cmsData.value = response.data
    console.log(response.data)
  })
  .catch(error => {
    console.log(error);
  });
</script>


<style lang="scss" scoped>
.head {
  font-size: 20px;
  h1 {
    color: rebeccapurple;
  }
}
</style>