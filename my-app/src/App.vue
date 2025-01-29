<template>
 <section>
    <img v-bind:src="picture" :width="size" :height="size"/><br/>
    <form @submit.prevent="submitForm">
      <label>ป้อนชื่อเล่น : </label>
      <input type="text" v-on:input="setNickName"/>
      <button type="submit">บันทึกชื่อเล่น</button>
    </form>
    <h1>ชื่อผู้สมัครงาน : {{ getFullName() }}</h1>
    <h1>ชื่อเล่น : {{ nickName }}</h1>
    <h1>นามสกุล : {{lastName }}</h1>
    <h1>อายุ : {{ age }}</h1>
    <h2>{{ 8700+200 }}</h2>
    <h2>ที่อยู่ : <span v-html="address"></span></h2>
    <a :href="social" target="_blank"><h2>Facebook</h2></a>
    <h2>งานอดิเรก :</h2>
    <ul>
      <li>{{ hobby[1] }}</li>
      <li>{{ hobby[2] }}</li>
    </ul>
    <h2>ข้อมูลพื้นฐาน</h2>
    <ul>
      <li>ข้อมูลเพศ : {{ general.gender }}</li>
      <li>น้ำหนัก : {{ general.weight }}</li>
      <li>ส่วนสูง : {{ general.height }}</li>
      <li>โรคประจำตัว : {{ general.status }}</li>
    </ul>
    <button @click="showWebName">คลิ๊กเพื่อแสดงชื่อเว็บ</button>
    <button @click.ctrl="addAge(10)">เพิ่มอายุ</button>
    <button @click.middle="downAge(5)">ลดอายุ</button>
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
      hobby:["อ่านหนังสือ","เล่นเกม","ฟังเพลง","ดูหนัง"],
      general:{gender:"Male",weight:60.5,height:175,status:false},
      webname: "Vue.js basic"
    }
  },
  methods:{
    getFullName(){
      return `${this.firstName}  ${this.lastName}`
    },
    showWebName(){
      alert(this.webname)
    },
    addAge(value){
      return this.age+=value
    },
    downAge(value){
      return this.age-=value
    },
    setNickName(event){
     this.nickName=event.target.value;
    },
    submitForm(){
      alert("บันทึกชื่อเล่นเรียบร้อย");
    }
  }
}
</script>

<style>

</style>
