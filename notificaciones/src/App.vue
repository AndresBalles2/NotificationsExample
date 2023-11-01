<script setup>
import { ref } from 'vue';

  let qty = ref (2)

  function addValue(){
    qty.value++
  }

  function restValue(){
    if(qty.value > 0){
    qty.value--
    }
  }
</script>

<template>
  <div class="wrapper">
    <div class="profile">
      <div class="ballon" v-if="qty > 0">{{ qty }}</div>
    </div>
    <div class="button-wrapper">
      <div class="button" @click="restValue">-</div>
      <div class="button" @click="addValue">+</div>
    </div>

    <div class="show" v-if="qty > 0">Me escribieron!! 😄🤗</div>
    <div class="show" v-else>Nadie me escribió 😢😔</div>

  </div>
</template>

<style scoped>

  .show{
    color: whitesmoke;
    text-align: center;
  }
  .wrapper{
    background-color:#2F3D40;
    width: 60%;
    border-radius: 12px;
    margin: 0 auto;
    padding-top: 18px;
    padding-bottom: 18px;
    overflow: hidden;
    border: 2px solid black;
  }

  .profile{
    background-image: url('https://pbs.twimg.com/profile_images/1318652224638124032/wrpp2Nl4_400x400.png');
    background-size: cover;
    width: 160px;
    height: 160px;
    margin: 0 auto;
    border-radius: 100%;
    position: relative;
    border: 2px solid black;
  }

  .ballon{
    width: 32px;
    height: 32px;
    background-color: #128c7e;
    border-radius: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: black;
    position: absolute;
    top: 10%;
    right: 4%;
    border: 2px solid black;
  }

  .button-wrapper{
    margin-top: 16px;
    text-align: center;
    margin-bottom: 16px;
  }

  .button{
    background-color: #128c7e;
    display: inline-block;
    padding: 4px 0;
    border-radius: 4px;
    width: 32px;
    margin: 0 8px;
    color: black;
    border: 2px solid black;
  }

  .button:hover{
    cursor: pointer;
    background-color: #075e54;
  }
</style>
