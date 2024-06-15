<template>
  <input type="text" v-model="userName" placeholder="Name">
  <input type="text" v-model="userPass" placeholder="Pass">
  <input type="text" v-model="userEmail" placeholder="Email">
    <p>{{ error }}</p>
    <button @click="sendDate">Yozish</button>
    <div v-if="userlist.length == 0">
      Bizda foydalanuvchilar hali yo'q
     </div>

    <User v-for="(el, index) in userList" :key="index" :user="el"/>
   
</template>


<script>
import User from './components/user.vue'
    
export default{
  components:{User},
  data() {
    return {
      error:'',
      userlist:[],
      userName:'',
      userPass:'',
      userEmail:'',
    }
  },
     methods:{
       sendDate(){
         if(this.userName==''){
         this.error ='Ism kiritilmagan';
         return;
         }else if(this.userPass == ''){
         this.error =  'Parol kiritilmagan';
         return;
         }else if(this.userEmail == ''){
         this.error =  'Email kiritilmagan';
         return;
       }
       this.error='';
       this.userlist.push({
       name:this.userName,
       pass:this.userPass,
       email:this.userEmail
       })
     }
  }}
</script>
  
<style scoped>
  .yozuv{
    width: 200px;
    color: bisque;
    font-weight: 900;
    font-style: italic;

    
  }
   input{
   font-size:20px;
   border:2px solid #2110d7;
   background-color:bisque;
   border-radius:10px;
   padding:5px;
   display:block;
   margin-top:0;
   }
   button{
   width:100px;
   text-aligan:center;
   padding:10px 0px;
   background-color:greenyellow;
   border-radius:15px;
   box-shadow:0px 0px 1px 3px blue;
   }
</style>