<template>
  <form @submit.prevent="submitForm" >

    <div class="form-control">
      <label for="emp-name">ชื่อพนักงาน</label>
      <input type="text" v-model.trim="employee.name" />
    </div>

    <div class="form-control">
      <label for="emp-salary">เงินเดือน</label>
      <input type="number" v-model="employee.salary" />
    </div>

    <div class="form-control">
      <label for="emp-department">ตำแหน่งงาน</label>
      <select v-model="employee.department">
        <option value="ฝ่ายการตลาด">ฝ่ายการตลาด</option>
        <option value="ฝ่ายการเงิน">ฝ่ายการเงิน</option>
        <option value="ฝ่ายการบุคคล">ฝ่ายการบุคคล</option>
      </select>
    </div>

    <div class="form-control">
      <h2>เพศ</h2>
      <div>
        <input type="radio" value="ชาย" v-model="employee.gender" />
        <label for="gender-name">ชาย</label>
      </div>
      <div>
        <input type="radio" value="หญิง"  v-model="employee.gender" />
        <label for="gender-name">หญิง</label>
      </div>
    </div>

    
    <div class="form-control">
      <h2>ทักษะด้านภาษา</h2>
      <div>
        <input type="checkbox" value="ภาษาอังกฤษ" v-model="employee.skill"  />
        <label for="skills-name">ภาษาอังกฤษ</label>
      </div>
      <div>
        <input type="checkbox" value="จีน" v-model="employee.skill"  />
        <label for="skills-name">จีน</label>
      </div>
       <div>
        <input type="checkbox" value="ญี่ปุ่น"  v-model="employee.skill" />
        <label for="skills-name">ญี่ปุ่น</label>
      </div>
    </div>



    <div>
      <button>บันทึกข้อมูล</button>
    </div>
  </form>
 
</template>

<script>
export default {
  name: "formComponent",
  data() {
    return {
      employee: {
        name: "Teera",
        salary: 15000,
        department: "",
        gender:"",
        skill:[]
      }
    }
  },methods:{
    submitForm(){
      const newEmp={
        name:this.employee.name,
        salary:this.employee.salary,
        department:this.employee.department,
        gender:this.employee.gender,
        skill:this.employee.skill
      }
      this.$emit("save",newEmp);
      this.resetForm();
    },resetForm(){
      this.employee.name=""
      this.employee.salary=0
      this.employee.department="ฝ่ายการตลาด"
      this.employee.gender=""
      this.employee.skill=[]
    }
  }
}
</script>

<style scoped>
form {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.25);
  background: #fff;
  padding: 2rem;
}

.form-control {
  margin: 0.5rem 0;
}

label {
  font-weight: bold;
}

input,
select {
  display: block;
  width: 100%;
  font: inherit;
  margin-top: 0.5rem;

}

button {
  font: inherit;
  background: rgb(35, 181, 60);
  cursor: pointer;
  padding: 0.75rem 1rem;
  color: white;
  border-radius: 15px;

}
input[type="radio"],[type="checkbox"]{
  display: inline-block;
  width: auto;
  margin-right: 1rem;
}
input[type="radio"]+label,
input[type="checkbox"]+label{
  font-weight: normal;
}
้้h2{
  font-size:1.5rem;
  margin: 1.5rem;

}
</style>