<template>
  <li>
    <img src="https://cdn-icons-png.flaticon.com/512/3135/3135715.png" alt="">
   <hr>
   <slot name="card-header"></slot>
   <slot name="card-button"></slot>
   <slot name="card-content"></slot>
  </li>
</template>

<script>
export default {

}
</script>

<style scoped>

li{ 
    margin: 1rem 0;
  font-size: 1.25rem;
  padding: 10px;
  color: #fff;
  border-radius: 25px;
  font-weight: bold;
  background: purple;
}
img{
    width: 100px;
    height: 100px;
}
</style>