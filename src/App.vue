<script setup lang="ts">
import { ref } from 'vue';

const color = ref('#333');

const randomColorGenerator = ():string => {
  const hexValues = ["1","2","3","4","5","6","7","8","9","A","B","C","D","E","F"];
  let generatedColor:string = "#"
  for (let i=0; i<6; i++) {
    generatedColor += hexValues[Math.floor(Math.random()*hexValues.length)]
  } 
  return generatedColor
};

const changeColor = () => {
  color.value = randomColorGenerator()
};


</script>

<template>
  <div class="h-screen flex justify-center items-center" :style="{ backgroundColor: color }">
    <div class="hero bg-base-200 w-max rounded-xl">
      <div class="hero-content text-center" :style="{ color: color }">
        <div class="max-w-md">
          <h1 class="text-5xl font-bold">Color Changer</h1>
          <p class="p-6">Click on the button below to change background color</p>
          <button @click="changeColor" class="btn btn-primary" :style="{ backgroundColor: color }">Change Color</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
