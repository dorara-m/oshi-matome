<template>
  <div class="top">
    <h1>hello my name is osshi!</h1>
    <ul>
      <li v-for="item in cmsData.contents" :key="item">
        <a :href="'/oshi/' + item.id">
          {{item.title}}
        </a>
      </li>
    </ul>
  </div>
</template>

<script setup>
import axios from 'axios'
let cmsData = ref({})
const route = useRoute()

axios.get(`https://uma-chat.microcms.io/api/v1/blog/`, {
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
