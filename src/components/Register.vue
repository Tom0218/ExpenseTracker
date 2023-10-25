<script>
export default{
    data(){
        return{
            Email:"",
            Password:"",
            showText:"",
            outputArr:"",
            userData:[],

        }
    },

    methods:{

        RegisterBtn(){
            let userinfo={
                account:this.Email,
                pwd:this.Password
            }
            this.userData.push(userinfo)
            let existingUserData = JSON.parse(localStorage.getItem("user")) || [];
            existingUserData.push(userinfo);
            localStorage.setItem("user", JSON.stringify(existingUserData));


            // if(JSON.parse(localStorage.getItem("user")) == null){//若為第一次使用localstorage
            //     localStorage.setItem("user",JSON.stringify(userData));
            //     showText = "註冊成功";

            // for(let i = 0;i<)
            // this.outputArr = JSON.parse(localStorage.getItem("user"));
            //     // console.log(this.outputArr[0].account)
            //     for(let i = 0;i<)
            },
        LogIn(){
            let x = 0
            this.$emit('changepage',x)
        }
    }
}

</script>

<template>
<div class="body">
    <div class="page">
            <div class="mainArea">
                <h1>Register</h1>
                <div class="emailbox">
                    <p >email</p>
                    <input type="text" v-model="Email">
                    <p></p>
                </div>
                <div class="namebox">
                    <p>name</p>
                    <input >
                </div>
                <div class="passwordbox">
                    <p>password</p>
                    <input type="text" v-model="Password" >
                </div>
                <div class="repeatpasswordbox">
                    <p >Repeatpassword</p>
                    <input id="reppwd">
                </div>
                <p>{{ showText }}</p>
                <div class="Signupbtnbox">
                    <button @click="RegisterBtn">Register</button>
                </div>
                <button type="button" @click="LogIn()">logIn</button>
            </div>
        </div>
</div>
</template>

<style lang="scss" scoped>
.body{
    height: 100%;
    margin: 0;
    background-color:gray;
    display: flex;
    align-items: center;
    justify-content: center;
}

p{
    font-size: 16pt;
    margin: 10px 0;
    font-weight: bold;
}

input{
    height: 25px;
    width: 300px;
    margin: 0;
    padding: 0;
}

a{
    color: black;
    text-decoration: none;
    display: flex;
    justify-content: end;
    font-weight: bold;
}

h1{
    text-align: center;
    margin-bottom: 30px;
}

.page{
    width: 500px;
    height: 500px;
    display: flex;
    justify-content: center;
    .mainArea{
        flex-direction: column;
    }
    
}

#end{
    text-align: center;
}
.Signupbtnbox{
    text-align: center;
}

</style>