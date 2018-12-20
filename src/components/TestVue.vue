<template>
  <div>
    <h1>{{name}}</h1>
    <p>{{employs.length}}</p>
    <h3>{{totalSalary}}</h3>
    <button v-on:click="increaseUser">INCREASE</button>
    <hr></hr>
    <div v-for="(emp,index) in employs"><!--วนลูป -->
      {{emp.id}}<h1>{{emp.name}}</h1><button v-on:click="deleteUser(emp.id)">DELETE</button><hr></hr>
    </div>
  </div>
</template>


<script>
  export default {
    name: 'testvue',
    data:()=>{
      return {
        name: 'niameen',
        count: 0,
        totalSalary:0,
        employs:[
          {name: 'niam',salary: 10000,id:1},
          {name: 'roon',salary: 15000,id:2},
          {name: 'wan',salary: 20000,id:3}
        ]
      }
    },
    methods:{
      increaseUser(){
        this.employs.push({name:'burn',salary: 30000,id:this.employs.length+1})
        this.sumSalary
      },
      deleteUser(index){
        this.employs = this.employs.filter((val)=> {
          return val.id !== index
        })
      }
    },
    computed:{
      sumSalary(){
        this.totalSalary = this.employs.reduce((acc,val)=>{
          return acc + val.salary
        },0)
      }
    }
  }
</script>
