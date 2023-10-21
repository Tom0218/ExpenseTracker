<script>
import AddObject from "./components/AddObject.vue"
export default {
  data() {
    return {
      plusNum: 0,
      neNum: 0,
      totalNum: 0,
      arr: [],
      addItem:[],
    }
  },
  components:{
    AddObject
  },

  methods: {
    NewItem(newinfo){
    
      this.arr = newinfo//把newinfo變數裡的資料綁定arr陣列
      this.addItem.push(this.arr)//把arr陣列push進additem陣列以便arr陣列清空並匯入新物件

      if(this.arr.Amount > 0){//判斷收入or 支出
        this.plusNum+=this.arr.Amount;
      }else{
        this.neNum +=this.arr.Amount;
        }
      this.totalNum = this.plusNum +  this.neNum;
    },
    DeleteItem(){

    }
  },




}
</script>

<template>
  <div class="bgArea">
    <div class="blueArea">
        <div class="mainArea">
          <h3 class="ExpenseTracker">Expense Tracker</h3>
          <h3 class="Kouhei">Kouhei</h3>
          <p class="Yourbalance">YOUR BALANCE</p>
          <h1 class="moneyyy">${{ totalNum }}</h1>
        </div>
    </div>
    <div class="whiteArea">
      <div class="top">

        <div class="Income">
          <h2>INCOME</h2>
          <h1>{{ this.plusNum }}</h1>
        </div>

        <div class="Expense">
          <h2>EXPENSE</h2>
          <h1>{{ this.neNum }}</h1>
        </div>

      </div>
      <div class="btn">
        <button type="button" class="numBtn" v-on:click="cool" id="Addtransaction">Add transaction</button>
      </div>
      <div class="content">
        <div class="block" v-for="item in addItem">
          <span class="itemName">{{ item.Text }} </span>
          <span class="moneyText">{{ item.Amount}} $</span>
          <button type="button" class="delBtn" @click="DeleteItem">Delete</button>
        </div>
      </div>
      
    </div>
  </div>
  <AddObject @getAddObj="NewItem"/>

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
    display: flex;
    justify-content: center;
    .ExpenseTracker{
      margin-top: 10vh;
      font-size: 28px;
      color: white;
    }
    .Kouhei{
      margin-top: 20vh;
      color: white;
      text-align: center;
      font-weight: bold;
    }
    .Yourbalance{
      margin-top: 5vh;
      color: white;
      text-align: center;
      font-weight: bold;
    }
    .moneyyy{
      margin-top: 2vh;
      color: white;
      text-align: center;
    }

    
  }

  .whiteArea {
    width: 60vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction:column;
    .content{
      width:60% ;
      height: 40vh;
      
      .block{
        display: flex;
        justify-content: space-between;
        align-items: center;
        font-size: 24pt;
        border: 3px #4b85a0 solid;
        border-radius: 10px;
        margin: 2% 0 ;
        position: relative;
        .moneyText{
          position: absolute;
          right: 20%;
        }
        .delBtn{
        
          height:25px;
          margin-right: 5px ;
          border: none;
          border-radius: 5px;
          background-color: #4b85a0;
          color: white;
        }
        .itemName{
          margin-left: 10px;
        }
        
      }
    }

    .top{
      width: 60%;
      margin: 0 20%;
      display: flex;
      justify-content: space-between;
      .Income{
        color: rgb(72, 165, 72);
        h1{
          text-align: center;
        }
      }
      .Expense{
        color: rgb(237, 52, 52);
        text-align: center;
      }
    

    }
    .numBtn{
      width: 200px;
      height: 30px;
      color: white;
      background-color: #4b85a0;
      border: none;
      border-radius: 5px;
    }

  }

}
</style>
<!-- git config --global user.email "you@example.com"
  git config --global user.name "Your Name" -->