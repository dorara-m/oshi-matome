<template>
  <div class="detail">
    <h1>oshi - 詳細</h1>
    <p>id: {{$route.params.id}}</p>
    <p>title: {{cmsData.title}}</p>
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
    // console.log(response.data)
  })
  .catch(error => {
    console.log(error);
  });
</script>