<template>
<div class="Login">
  <HeaderAuth />

  <p class="LoginTitle">JUST DO IT.</p>

  <p class="LoginsubTitle">すぐやりたくなるToDoリスト</p>

  <div class="sub">
  <button @click="openModal" class="loginDo">ログインする</button>
    <div id="overlay" v-if="show">
      <div id="content">
        <input placeholder="メールアドレス" type="email" />
       <input placeholder="パスワード" type="password" />
        <button id="close" @click="closeModal">ログイン</button>
      </div>
  </div>
</div>
</div>
</template>

<script>
import HeaderAuth from "../components/HeaderAuth";
export default {
  data() {
    return {
      show: false
    };
  },
  methods: {
    openModal() {
      this.show = true;
    },
    closeModal() {
      this.show = false;
    }
  },
    components: {
   HeaderAuth

  }
};
</script>


<style scoped>

.LoginTitle {
font-size: 100px;
font-weight:900;
position:absolute;
top:30%;
left:27%;
}

.LoginsubTitle {
font-size: 20px;
font-weight:900;
position: absolute;
top: 45%;
left: 40%;
padding: 15px;
} 

.loginDo{
 margin: 20px;
}

button {
 width: 100px;
 padding: 8px 0 10px;
 color: rgb(250, 249, 249);
 font-weight: 500px;
 background-color: #fda634;
 border-radius: 20px;
 border: 3px solid #fff3f3;
 cursor: pointer;
 position:absolute;
 top: 50%;
 left: 48%;
}

#overlay {
  display: flex;
  align-items: center;
  justify-content: center;
}
.form {
  text-align: center;
}


#content {
  height:300px;
  width:800px;
  text-align: center;
  z-index: 2;
  margin-top: 50px;
  margin-left: 20px;
  padding: 10px;
  background: rgb(255, 254, 254);
}

input {
  margin: 3%;
  width: 80%;
  border-radius: 10px;
  padding:10px;
  border: 2px solid #fda634;
  color: rgb(5, 5, 5);
}

#close{
  border: 2px solid #fda634;
  background-color: white;
  color: #fda634;
}

</style>