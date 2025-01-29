<template>
 <section>
    <img v-bind:src="picture" :width="size" :height="size"/><br/>
    <h1>ชื่อผู้สมัครงาน : {{ getFullName }}</h1>
    <h1>นามสกุล : {{lastName }}</h1>
    <h1>อายุ : {{ age }}</h1>
    <h1>เงินเดือน : {{ salary }} บาท</h1>
    <button @click="addSalary(5000)">เพิ่มเงินเดือน</button>
    <h1>ตำแหน่งงาน : {{ getDepartment }}</h1>
    <button @click="toggleVisible">{{isVisible ? "ซ่อน":"แสดง"}}รายละเอียดพนักงาน</button>
    <article v-show="isVisible">
      <h2>{{ 8700+200 }}</h2>
    <h2>ที่อยู่ : <span v-html="address"></span></h2>
    <a :href="social" target="_blank"><h2>Facebook</h2></a>
    <p v-if="hobby.length === 0">ไม่มีงานอดิเรก</p>
    <div v-else>
      <p>งานอดิเรก :</p>
    <ul>
      <li v-for="(item,index) in hobby" :key="index">{{ item }} </li>
    </ul>

    </div>
    <h2>ข้อมูลพื้นฐาน</h2>
    <ul>
      <li v-for="(item,key) in general" :key="key">{{ key }} - {{ item }}</li>
    </ul>
    </article>

 </section>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      firstName: "Pream1100",
      lastName: "Nilpan",
      nickName: "",
      age: 15,
      address:"<i>Bangkok</i>",
      picture: "https://cdn-icons-png.flaticon.com/512/4042/4042171.png",
      size:100,
      social:"https://www.facebook.com/preammaerq/",
      hobby:["อ่านหนังสือ","เล่นเกม","ทำอาหาร","ดูหนัง","เลี้ยงแมว"],
      general:{gender:"Male",weight:60.5,height:175,status:false},
      webname: "Vue.js basic",
      isVisible: false,
      salary: 20000
    }
  },
  methods:{
    toggleVisible(){
      this.isVisible= !this.isVisible;
    },
    addSalary(value){
      this.salary += value;
    }
  },
  computed:{
    getFullName(){
      return `${this.firstName}  ${this.lastName}`
    },
    getDepartment(){
      return this.salary >= 35000 ? "Project manager" : "Programmer" 
    }
  }
}
</script>

<style>

</style>
