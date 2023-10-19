<script>
export default{
    data(){
        return{
            newinfo:{
                Text:"",
                Amount:"",
            }
            
        }
    },
    methods:{
        Toindex(){
            this.$emit('New',this.newinfo);
        }
    }
}

</script>

<template>
    <div class="popup">
    <div class="popup-content">
        <div class="showArea">
            <div class="inputArea">
                <p>Text</p>
                <input type="text" v-model="this.NewObj.Text">
                <p>Amount</p>
                <input type="text" v-model="this.NewObj.Amount">
                <div class="btn">
                <button type="button" @click="Toindex">Add transaction</button>
                </div>    
            </div>
        </div>
        <slot></slot>
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