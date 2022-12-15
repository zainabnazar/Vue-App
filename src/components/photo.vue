<template>
<div class ="photo">
  <!-- <h3>{{photo.name}}</h3> -->
  <Card style="width: 25em" class="card_style">
            <template #header>
              <img :src="photo.img" width="300" height="300">
              
            </template>
            <template #title>
                {{photo.name}}
            </template>
  
            <template #footer>
                <Button @click="onRemove(photo.id)" label="Remove" class="p-button-danger" />
                <Button icon="pi pi-heart" v-bind:class= "[photo.isFavorite? 'p-button-rounded p-button-help p-button-danger' : 'p-button-rounded p-button-help p-button-danger p-button-outlined' ]" style="margin-left: .5em" />
            </template>
        </Card>
</div>
  
</template>

<script>
export default {
props:{
  photo:Object
},
components:{},
methods:{
  onRemove(id){
    this.$emit("remove-photo",id);
  }
}
}
</script>

<style>
.card_style{
  align-items: center;
  margin: 100px 200px;
}
</style>