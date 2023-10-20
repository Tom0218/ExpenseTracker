<script>
export default{
    data(){
        return{
            newItem:{
                Text:"",
                Amount:"",
                
            }
            
        }
    },
    methods:{
        addItem(){
            this.$emit('dog1',this.newItem);
            this.newItem={};
            }

        },
    }


</script>

<template>
        <div class="showArea">
            <div class="inputArea">
                <p>Text</p>
                <input type="text" v-model="this.newItem.Text">
                <p>Amount</p>
                <input type="number" v-model="this.newItem.Amount">
                <div class="btn">
                <button type="button" @click= "addItem" >Add transaction</button>
                </div>    
            </div>
        </div>
</template>

<style lang="scss" scoped>
    p{
        color: #3C7FA5;
        margin: 0;
        font-size: 20pt;
    }
    input{
        margin: 0;
        width: 300px;
        height: 30px;
        font-size: 16pt;
        border-radius: 10px;
        border-color: #3C7FA5;
    }
    button{
        color: white;
        background-color: #3C7FA5;
        border-radius: 10px;
        height: 30px;
        font-weight: bold;
        border: none;
        
    }
    
    .showArea{
        height: 300px;
        width: 500px;
        display: flex;
        justify-content: center;
        border-radius: 20px;
        border: 1px black solid;
        .inputArea{
            height: 200px;
            width: 300px;
            margin-top: 10%;
            .btn{
                display: flex;
                justify-content: center;
                margin-top: 10%;
            }

    
        }
    }
    
</style>