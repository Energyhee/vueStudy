<template>
  <div class="list-wrapper">
    <h2>직원 목록</h2>
    <ul class="staff-list">
      <li v-for="(person, i) in group" :key="i" class="staff-item">
        <div class="pic">
          <img :src="person.pic" :alt="person.name">
        </div>
        <h3 class="name">이름 : {{person.name}}</h3>
        <p class="age">나이 : {{person.age}}</p>
        <p class="area">지역 : {{person.area}}</p>
        <button v-on:click="staffCheck(i)">클릭</button>
        <div v-if="person.sta == true">출근</div>
      </li>
    </ul>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data(){
    return {
      group : [
        {
          area : '강남',
          name : 'Staff01',
          age : 22,
          pic : require('./assets/staff01.jpg'),
          sta : false
        },
        {
          area : '구로',
          name : 'Staff02',
          age : 24,
          pic : require('./assets/staff02.jpg'),
          sta : false
        },
        {
          area : '강서',
          name : 'Staff03',
          age : 26,
          pic : require('./assets/staff03.jpg'),
          sta : false
        },
        {
          area : '영등포',
          name : 'Staff04',
          age : 28,
          pic : require('./assets/staff04.jpg'),
          sta : false
        }
      ],
    }
  },
  methods: {
    staffCheck(idx){
      this.group[idx].sta = (this.group[idx].sta == false ? true : false);
    }
  },  
  components: {
    
  }
}
</script>

<style>
.list-wrapper {
  max-width: 700px;
  margin: 0 auto;
}
.staff-list {
  display: flex;
  flex-wrap: wrap;
  gap: 40px 10px;
  padding: 0;
}
.staff-item {
  flex: calc((100% - 10px) / 2);
  list-style: none;
}
.staff-item .pic img {
  width: 80%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
