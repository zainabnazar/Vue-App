<template>
  <div class="photos">
      <div v-for="photo in photos" :key="photo.id">
          <photo @remove-photo="$emit('remove-photo',photo.id)" :photo="photo"/>
      </div>
  </div>
</template>

<script>
import photo from "./photo.vue";

export default {
    props:{
        photos: Array,
    },
    components:{photo},
    emits: ["remove-photo"],
}
</script>

<style>

</style>