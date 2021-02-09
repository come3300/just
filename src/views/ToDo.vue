<template>

<div class="Todo1">
  <HeaderAuth2 />
  <div class="create">
    <p class="subtitle">To Do create</p>
    <div class="search1">
      <p>①</p>
      <input class ="todomake1" v-model="newtask" placeholder="今日中にすること" type="text" />
      <button v-on:click="doAdd1" class="make1">作成</button>
    </div>

    <div class="search2">
      <p>②</p>
      <input class ="todomake2" placeholder="１週間以内にすること" type="text" v-model="newmake"  />
      <button v-on:click="doAdd2" class="make2">作成</button>
    </div>
  </div>

  <div class="ToDotoday">
    <p>①今日中にすることリスト</p>
    <ul>
      <li v-for="(todo,index) in todos" :key="index">
         <input type ="checkbox" v-model="index[task]">
        <p class="task1" input type="checkbox">
          {{todo.task}}
        </p>
          <button  v-on:click="showdetail" class="detail">
            詳細
          </button>
          <div class="det" v-if="show">
            <open @close="it"></open>
          </div>
          <button  v-if="todos"  v-on:click="deleteTodo(index)" class="del" >
            削除
          </button>
      </li>
    </ul>
  </div>
 


  <div class="ToDoweek">
    <p>②１週間以内にすることリスト</p>
    <ul>
      <li v-for="(get,index) in makes" :key="index">
        <!-- todoの詳細を入力できるフォームを描画させる処理 -->
        <input type ="checkbox" v-model="index[make]">
        <p class="task2">
          {{get.make}}
        </p>
        <button  v-on:click="showdetail" class="detail">
            詳細
          </button>
          <div class="det" v-if="show">
            <open @close="it"></open>
          </div>
           <button  v-if="makes"  v-on:click="deleteweekdo(index)" class="del">
            削除
          </button>
        
      </li>
    </ul>

  </div>
</div>

</template>

<script>
import HeaderAuth2 from "../components/HeaderAuth2";
import open from "../components/open.vue";
export default {
  data() {
    return {
      newtask:"",
      newmake:"",
      todos:[],
      makes:[],
      weekdo: '',
      detail:[],
      show: false
    };
  },
  methods:{
    doAdd1(){
      this.todos.push({
      task: this.newtask
      });
      // 入力内容初期化
      this.newtask = '';
    },
    doAdd2(){
      this.makes.push({
        make: this.newmake
      });
      // 入力内容初期化
      this.newmake = '';
    },

    deleteTodo(index){
     this.todos.splice(index,1);
     },

     deleteweekdo(index){
     this.makes.splice(index,1);
     },

     it(){
       this.show=false
     },
     
     showdetail(){
      this.show=true
    }
  },
  components: {
    HeaderAuth2,
    open
  }

}
    
</script>
<style scoped>
.Todo1 {
  display: flex;
  }

.create{
  position: relative;
  right: 18%;
  top: 100px;
  background: white;
  width:350px;
  height: 500px;
  border-radius: 20px;
  margin-top: 10px;
  margin-bottom: 20px;
  
}

.subtitle{
  color: #fda634;
  padding: 20px 0;
  position:relative;
  right: 22%;
  font-size: 30px;
  font-weight: bold;
  border-bottom: 3px dotted #fda634;
  width: 500px;
  display: block;
  text-align: center;

}

.search1{
  margin:20px auto;
  width: 80%;
  height: 90px;
  padding: 8px;
  border: 3px solid rgb(190, 190, 190);
  color: rgb(165, 164, 164);
  position: absolute;
  top: 20%;
  left: 8%;
}

.search1 p{
 color: rgb(165, 164, 164);
 font-weight: bold;
 font-size: 30px;
 padding: 25px 1px;
}

.todomake1{
 width: 230px;
 height: 50px;
 border: 2px solid rgb(190, 190, 190);
 border-radius: 7px;
 text-align: center;
 position: absolute;
 bottom: 23%;
 left: 17%;
 font-size: 20px;
 color: black;

}

.make1 {
color: #fcfbfa;
font-weight: bold;
background-color: #fda634;
width: 70px;
border: 2px solid #fda634;;
border-radius: 5px;
position: absolute;
right: 0%;
top: 115%;
}

.search2{
  margin:20px auto;
  width: 80%;
  height: 90px;
  padding: 8px;
  border: 3px solid rgb(190, 190, 190);
  color: rgb(165, 164, 164);
  position: absolute;
  top: 60%;
  left: 8%;
}

.search2 p{
 color: rgb(165, 164, 164);
 font-weight: bold;
 font-size: 30px;
 padding: 25px 1px;
}

.todomake2{
 width: 230px;
 height: 50px;
 border: 2px solid rgb(190, 190, 190);
 border-radius: 7px;
 text-align: center;
 position: absolute;
 bottom: 23%;
 left: 17%;
 font-size: 20px;
 color: black;

}

.make2 {
color: #fcfbfa;
font-weight: bold;
background-color: #fda634;
width: 70px;
border: 2px solid #fda634;;
border-radius: 5px;
position: absolute;
right: 0%;
top: 115%;
}

.ToDotoday{
  background-color: #fdfdfd;
  width:1500px;
  height: 500px;
  border-radius: 20px;
  position: relative;
  right: 8%;
  top: 100px;
  margin-top: 10px;
  margin-bottom: 20px;
}
.ToDotoday p{
 color: #fda634;
 text-align: center;
 font-weight: bold;
 font-size: 23px;
 padding: 23px 2px;
 
}

.ToDoweek{
  background-color: #fdfdfd;
  width:1500px;
  height: 500px;
  border-radius: 20px;
  position: relative;
  right: 5%;
  top: 100px;
  margin-top: 10px;
  margin-bottom: 20px;
}

.ToDoweek p{
 color: #fda634;
 text-align: center;
 font-weight: bold;
 font-size: 20px;
 padding: 26px 2px;

}

.task1 {
    box-sizing: border-box;
    cursor: pointer;
    display: inline-block;
    padding: 5px 30px;
    position: relative;
    width: auto;
}

.task2{
    box-sizing: border-box;
    cursor: pointer;
    display: inline-block;
    padding: 5px 30px;
    position: relative;
    width: auto;
}


.del{
background: #fda634;
color: #fcfbfa;
font-weight: bold;
border: 2px solid #fda634;;
border-radius: 5px;
margin-left:5px;
}

.detail{
 background: #fda634;
color: #fcfbfa;
font-weight: bold;
border: 2px solid #fda634;;
border-radius: 5px;
margin-left:5px;
}
.click{
  background: #fff;
  
}


ul{
  list-style: none;
  color: #fda634;
   }

li{
  width: 95%;
  height: 70px;
  border: 3px solid #fda634;
  color: #fda634;
  margin: 5px;
  
  
  }

@media screen and (max-width : 480px)
{

.Todo1{
  flex-wrap: wrap;
  overflow: hidden;
}

.create{
width: 100%;
float: none;
margin-left: 25%;
margin-top: 0;
top: 50%;
}


.ToDotoday{
width: 100%;
float: none;
overflow: hidden;
margin-left: 15%;
top: 10%;
}

.ToDoweek{
width: 100%;
float: none;
margin-left: 13%;
top: 10%;
}
}


@media screen and (max-width : 768px){

  .create{
  width:300px;
  height:500px;
 }

 .subtitle{
  font-size: 25px;
  text-align: center;
  position: relative;
  right: 98px;
}

.todomake1{
 width: 180px;
 font-size: 15px;
}

.todomake2{
width: 180px;
font-size: 15px;
}

.search1 p{
  font-size: 20px;
  margin-top:10px;
}

.search2 p{
 font-size: 20px;
 margin-top:10px;
}

.ToDotoday{
 width: 80%;
 display:block;
}

.ToDotoday p{
 font-size: 20px;
}



.ToDoweek{
   width: 80%;
   display:block;
}





}




  

</style>

