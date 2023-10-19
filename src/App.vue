<script>
import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      plusNum: 0,
      neNum: 0,
      totalNum: 0,
      arr: [],
    }
  },


methods: {



cool(){
  const Userinput = document.getElementById("Add transaction");
  //let Addtransaction = parseInt(Userinput.value);

  if (Addtransaction > 0) {
    let obj = {
      name :"good",
      money : 50,
  }
        this.arr.push(obj);
      }else {
        let obj2 = {
          name :"bad",
          money : -10,
          
          }
          this.arr.push(obj2);
        }

      
      
      
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
          <h1>{{ plusNum }}</h1>
        </div>


        <div class="Expense">
          <h2>EXPENSE</h2>
          <h1>{{ neNum }}</h1>
        </div>





      </div>
      <div class="btn">
        <button type="button" class="numBtn" v-on:click="cool" id="Addtransaction">Add transaction</button>
      </div>
      <div class="content">
        <div class="block" v-for="item in arr">
          <span class="itemName">{{ item.name }}</span>
          <span class="moneyText">${{ item.money }}</span>
          <button type="button" class="delBtn">Delete</button>
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
          right: 18%;
        }
        .delBtn{
          width: 15%;
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
