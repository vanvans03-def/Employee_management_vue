<template>
  <cardComponent>

    <template v-slot:card-header>
      <h1> {{ name }} </h1>
      <p>เพศ: {{ gender }}</p>
    </template>

    
    <template v-slot:card-content>
       <p>เงินเดือน: {{ salary }} บาท ตำแหน่งงาน: {{ department }}</p>
      <p>ทักษะด้านภาษา: {{skill}}</p>
   </template>

  </cardComponent>
</template>

<script>
import cardComponent from './cardComponent.vue'
export default {
  name: "Person-data",
  components: {
    cardComponent,
  },
  data() {
    return {
      "msg": "ข้อมูลพนักงานแต่ละคน"
    }
  }, props: {
    id: {
      type: Number
    },
    name: {
      type: String,
      required: true
    },
    salary: {
      type: Number,
      default: 14000
    },
    department: {
      type: String,
      required: true
    },
    gender:{
      type:String
    },
    skill:{
      type: Array
    }
   
  }
}
</script>

<style scoped>
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0066;
  background: #ff0066;
  color: white;
  padding: 0.05 1rem;
  box-shadow: 1px 1px 1px 2px rgba(0, 0, 0, 0.26);
  border-radius: 25px;

}

.fade-enter-from {
  opacity: 0;

}

.fade-enter-active {
  transition: all 0.5s linear;
}
</style>
  
