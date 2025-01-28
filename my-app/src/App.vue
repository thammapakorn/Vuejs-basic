<template>
 <section>
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
      address:"<i>Bangkok</i>"
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
