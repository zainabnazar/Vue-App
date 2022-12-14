<script>
import photos from "../components/photos.vue";
export default {
  name:"Home",
  components:{ photos },
  data(){
    return {
      photos:[
        {
          id: 1,
          name: "Rose",
          img:"https://www.google.com/url?sa=i&url=https%3A%2F%2Fcommons.wikimedia.org%2Fwiki%2FFile%3ARose_flower.jpg&psig=AOvVaw1DrNVclwVSOI_ZaWJA8Vld&ust=1671112098196000&source=images&cd=vfe&ved=0CA8QjRxqFwoTCMCZ9-mf-fsCFQAAAAAdAAAAABAG",
          isFavorite: true,
        },
        {
          id: 2,
          name: "Orchid",
          img:"https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.serenataflowers.com%2Fpollennation%2Fhow-to-care-for-orchids%2F&psig=AOvVaw0si0iuK8IOgw7gnx5BBIY2&ust=1671112297352000&source=images&cd=vfe&ved=0CA8QjRxqFwoTCPD62Mig-fsCFQAAAAAdAAAAABAG",
          isFavorite: false,
        },
      ],
  }
  }
}
</script>

<template>
  <div class="home">
  </div>
  <photos v-bind:photos="photos"/>
</template>
