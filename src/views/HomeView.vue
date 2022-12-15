<script>
import photos from "../components/photos.vue";
export default {
  name:"Home",
  components:{ photos },
  methods:{
    removePhoto(id){
     this.photos= this.photos.filter((photo)=> photo.id !==id);
    },
    async fetchPhotos(){;
      const res = await fetch("https://639b148631877e43d6818843.mockapi.io/photos")
      const data = await res.json();
      return data;
    },
    async fetchPhoto(id){;
      const res = await fetch(`https://639b148631877e43d6818843.mockapi.io/photos/${id}`)
      const data = await res.json();
      return data;
    }
  },
  data(){
    return {
      photos:[],
  }
  },
  async created(){
    this.photos= await this.fetchPhotos();
  }
}
</script>

<template>
  <div class="home">
  </div>
  <photos @remove-photo="removePhoto" v-bind:photos="photos"/>
</template>
