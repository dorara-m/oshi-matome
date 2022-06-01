<template>
  <div class="detail">
    <Container>
      <div class="head">
        <h1>{{cmsData.title}}</h1>
        <p>Oguri cap</p>
        <img src="/images/oguri.jpg" alt="">
        <div class="label">急上昇↑</div>
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
    </Container>
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
.detail {
  padding: 50px 0;
}

.head {
  margin-bottom: 30px;
  display: grid;
  grid-template-columns: 1fr 90px;
  position: relative;
  h1 {
    font-size: 30px;
    font-weight: bold;
  }
  p {
    margin-top: -20px;
    font-size: 16px;
  }
  img {
    width: 90px;
    border-radius: 50%;
    grid-row: 1 / 3;
    grid-column: 2 / 3;
  }
  .label {
    color: #FD1515;
    font-weight: bold;
    position: absolute;
    right: 0;
    bottom: 0;
  }
}
</style>