<template>
 <div class="header flex">
   <div class="left">
   </div>
   <div class="right flex">
     <p id="new1" @click="$router.push('/signup')">新規登録</p>
     <p id="new2" @click="$router.push('/')">ログイン</p>
   </div>
 </div>
</template>

<style scoped>

#new1 {
  border-radius: 10px;
  padding:10px;
  border: 2px solid #fff3f3;
}

#new2{
  border-radius: 10px;
  padding:10px;
  border: 2px solid #fff3f3;
}

.right {
 align-items: center;
 color:white;
}
.right p {
 margin-right: 20px;
 cursor: pointer;
}
.header {
 margin: 20px;
}
.logo {
 width: 150px;
 cursor: pointer;
}
.flex {
 display: flex;
 justify-content: space-between;
}
</style>