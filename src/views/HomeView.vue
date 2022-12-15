<script>
import photos from "../components/photos.vue";
export default {
  name:"Home",
  components:{ photos },
  methods:{
    removePhoto(id){
     this.photos= this.photos.filter((photo)=> photo.id !==id);
    },
  },
  data(){
    return {
      photos:[
        {
          id: 1,
          name: "Rose",
          img: "https://upload.wikimedia.org/wikipedia/commons/8/8b/Rose_flower.jpg",
          isFavorite: true,
        },
        {
          id: 2,
          name: "Orchid",
          img:"https://blog.serenataflowers.com/pollennation/wp-content/uploads/2015/04/how-to-care-for-orchids-FT.png",
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
  <photos @remove-photo="removePhoto" v-bind:photos="photos"/>
</template>
