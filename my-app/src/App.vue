<template>
 <section>
    <img v-bind:src="picture" :width="size" :height="size"/><br/>
    <h1>ชื่อผู้สมัครงาน : {{ getFullName() }}</h1>
    <h1>นามสกุล : {{lastName }}</h1>
    <h1>อายุ : {{ age }}</h1>
    <h2>{{ 8700+200 }}</h2>
    <h2>ที่อยู่ : <span v-html="address"></span></h2>
    <a :href="social" target="_blank"><h2>Facebook</h2></a>
    <p v-if="hobby.length === 0">ไม่มีงานอดิเรก</p>
    <div v-else>
      <p>งานอดิเรก :</p>
    <ul>
      <li>{{ hobby[0] }}</li>
      <li>{{ hobby[1] }}</li>
      <li>{{ hobby[2] }}</li>
    </ul>

    </div>
    <h2>ข้อมูลพื้นฐาน</h2>
    <ul>
      <li>ข้อมูลเพศ : {{ general.gender }}</li>
      <li>น้ำหนัก : {{ general.weight }}</li>
      <li>ส่วนสูง : {{ general.height }}</li>
      <li>โรคประจำตัว : {{ general.status }}</li>
    </ul>
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
      hobby:["อ่านหนังสือ"],
      general:{gender:"Male",weight:60.5,height:175,status:false},
      webname: "Vue.js basic"
    }
  },
  methods:{
    getFullName(){
      return `${this.firstName}  ${this.lastName}`
    }
  }
}
</script>

<style>

</style>
