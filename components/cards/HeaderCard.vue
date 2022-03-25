<template>
  <div class="custom__card" :style="{ 'background-color': color }">
      <div class="d-flex align-center">
          <v-icon :style="{ 'color': color }" class="primary__icon" >{{primaryIcon}}</v-icon>
          <h3 class="ml-2">{{mainTitle}}</h3>
      </div>
      <p v-if="description == null" style="font-size: 35px; font-weight:700" class="ml-8 mt-1">0</p>
      <p v-if="description != null" style="font-size: 15px; font-weight:700" class="ml-8 mt-2">{{description}}</p>
      <p v-if="description1 != null" style="font-size: 15px; font-weight:700" class="ml-8 mt-1">{{description1}}</p>
      <div style="margin-top:-20px" class="d-flex">
          <v-icon dark>{{SecondaryIcon}}</v-icon>
          <p class="ml-2 mt-4">{{subTitle}}</p>
      </div>
  </div>
</template>

<script>
export default {
    name: 'HeaderCard',
    props : ['color', 'mainTitle','subTitle', 'primaryIcon', 'SecondaryIcon', 'description', 'description1']
}
</script>

<style>
.custom__card {
  max-width: 356px;
  padding: 20px;
  color: white;
  border-radius: 15px;
  height: 191px;
  padding: 15px;
}
.primary__icon {
  background-color: white;
  border-radius: 50%;
  padding: 9px;
}
</style>