<template>
  <header>
    <h1>ระบบจัดการข้อมูลพนักงาน</h1>
  </header>

   <formComponent @save="insertEmployee"></formComponent>

  <section class="employees-content" v-if="employees.length>0" >
    <h2>ข้อมูลพนักงาน</h2>
    <ListData :employees="employees" />
  </section>
</template>

<script>
import ListData from './components/ListData.vue'
import formComponent from './components/formComponent.vue'
export default {
  name: "App",
  components: {
    ListData,
   formComponent

  },data(){
    return{
      employees:[]
    }
  },methods:{
    insertEmployee(data){
      this.employees.push(data);
    }
  }
}
</script>

<style>
*{
  box-sizing: border-box;
}
body{
  margin:0;
}
header{
  box-shadow: 0 2px 8px rgba(0,0,0,0.26) ;
  margin: 3rem;
  border-radius: 10px;
  padding:1rem;
  background-color:rgb(238, 50, 103) ;
  color:white;
  text-align: center;

}
.employees-content{
   box-shadow: 0 2px 8px rgba(0,0,0,0.26) ;
  margin: 3rem;
  border-radius: 10px;
  padding:1rem;
  text-align: center;
}
.employees-content h2{
  font-size: 2rem;
  border-bottom:2px solid;
  margin: 0 0 1rem 0 ;
}
</style>
