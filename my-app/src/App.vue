<template>
 <section>
    <img v-bind:src="picture" :width="size" :height="size"/>
    <h1>ชื่อผู้สมัครงาน : {{ getFullName() }}</h1>
    <h1>นามสกุล : {{lastName }}</h1>
    <h2>{{ 8700+200 }}</h2>
    <h2>ที่อยู่ : <span v-html="address"></span></h2>
 </section>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      firstName: "Pream1100",
      lastName: "Nilpan",
      age: 15,
      address:"<i>Bangkok</i>",
      picture: "https://cdn-icons-png.flaticon.com/512/4042/4042171.png",
      size:100
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
