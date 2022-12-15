<script>
import photos from "../components/photos.vue";
export default {
  name:"Home",
  components:{ photos },
  methods:{
     async removePhoto(id){
      const res = await fetch(`https://639b148631877e43d6818843.mockapi.io/photos/${id}`,
       {
         method: "DELETE",
       });
      if (res.status === 200){
        this.photos= this.photos.filter((photo)=> photo.id !==id)
      } else{
      console.log("error")  
      } 
    },
    async fetchPhotos(){;
      const res = await fetch("https://639b148631877e43d6818843.mockapi.io/photos")
      const data = await res.json();
      console.log(data);
      return data;
    },
    async fetchPhoto(id){;
      const res = await fetch(`https://639b148631877e43d6818843.mockapi.io/photos/${id}`)
      const data = await res.json();
      console.log(data);
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
