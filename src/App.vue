<script>
import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      plusNum: 0,
      neNum: 0,
      totalNum: 0,
      arr: [],
      Title:"Expense Tracker",
      Title2:"Kouhei",
      Title3:"Your Balance"
    }
  },
  methods: {
    cool() {
      let obj = {
        name: "Breakfast",
        money: 65
      }

      let obj2 = {
        name: "lunch",
        money: 90
      }

      let obj3 = {
        name: "Design Case",
        money: 10000
      }

      let obj4 = {
        name: "BlueRay Video",
        money: 1420
      }
      this.arr.push(obj)
      this.arr.push(obj2)
      this.arr.push(obj3)
      this.arr.push(obj4)
    }
  },
  components: {
    HelloWorld
  }
}
</script>

<template>
  <div class="bgArea">
    <div class="blueArea">
      <h1 class="titleZone">{{ Title }}</h1>
      <h1 class="titleZone2">{{ Title2 }}</h1>
      <h1 class="titleZone3">{{ Title3 }}</h1>
      <h1 class="titleZone4">{{ totalNum }}</h1>
    </div>
    <div class="whiteArea">
      <div class="top">
        <div class="topLeft">
          <h1 class="topLeftText">INCOME</h1>
          <h1>{{ plusNum }}</h1>
        </div>
        <div class="topRight">
          <h1 class="topRightText">EXPENSE</h1>
          <h1>{{ neNum }}</h1>
        </div>
      </div>
      <div class="btn">
        <button type="button" class="numBtn" v-on:click="cool">Add transaction</button>
      </div>
      <div class="content">
        <div class="block" v-for="item in arr">
          <span>{{ item.name }}</span>
          <span>{{ item.money }}</span>
          <button type="button" class="blockBtn">Delete</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.bgArea {
  width: 100%;
  height: 100vh;
  display: flex;

  .blueArea {
    width: 40vw;
    height: 100vh;
    background-color: #4b85a0;
    

    h1{
      color:white;
    }

    .titleZone{
      display:flex;
      justify-content: center;
      align-items: center;
      height:15vw;
    }

    .titleZone2{
      display:flex;
      justify-content: center;
      align-items: center;
    }

    .titleZone3{
      display:flex;
      justify-content: center;
      align-items: center;
      margin-top:7%;
    }

    .titleZone4{
      display:flex;
      justify-content: center;
      align-items: center;
    }



  }

  .whiteArea {
    width: 60vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction:column;

    .top{
      width:100%;
      height:30%;
      display:flex;
      justify-content:space-around;
      

    .topLeft{
      color:rgb(33, 137, 75);
    }

    .topRight{
      color:rgb(164, 52, 127);
    }
    }

    .numBtn{
      background-color:rgb(102, 102, 176);
      color:white;
      font-size:24pt;
      margin-bottom:10%;
      border-radius:5px 5px 5px 5px;
    }
    .content{
      width:60% ;
      height: 40vh;
      color:#3C7FA5;
      
      .block{
        display: flex;
        justify-content: space-between;
        font-size: 24pt;
        border:2px solid #3C7FA5;
        margin-bottom:3%;

        .blockBtn{
          background-color:rgb(19, 19, 79);
          color:white;
          font-size:20pt;
        }
      }
    }
  }

}
</style>
