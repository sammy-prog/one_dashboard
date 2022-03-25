<template>
  <div class="d-flex stream__card align-center ml-2">
    <v-icon dark>{{icon}}</v-icon>
    <div class="ml-4 mt-4">
        <p style="font-size:18px;">{{title}}</p>
        <p style="margin-top:-15px;font-size:30px;font-weight:700">0</p>
    </div>     
  </div>
</template>

<script>
export default {
    name: 'SmallStreamCard',
    props: ['icon', 'title']
}
</script>

<style>
.stream__card {
  border: 1px solid #E8E7E7;
  padding: 15px;
  padding-bottom: 0px;
  border-radius: 10px;
  width: 290px;
  height: 100px;
}
.stream__card i{
  background-color: #FFC88E;
  padding-left: 14px;
  padding-right: 14px;
  border-radius: 10px;
  height: 60px;
}
</style>