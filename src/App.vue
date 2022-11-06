<template>
  <div class="content">
    <AdviceBox/>
  </div>
</template>

<script>
import AdviceBox from './components/AdviceBox.vue';
export default {
  components: {
    AdviceBox
  }
}
</script>

<style>
body{
    box-sizing: border-box;
    background-color: hsl(218, 23%, 16%);
    display: flex;
    height: 100vh;
    width: 100vw;
    margin: 0;
    justify-content: center;
    align-items: center;
}
</style>
