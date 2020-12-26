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
   <input class ="todomake2" placeholder="１週間以内にすること" type="text" v-model="task"  />
   <button v-on:click="doAdd2" class="make2">作成</button>
   </div>
  </div>

  <div class="ToDotoday">
   <p>①今日中にすることリスト</p>
   <ul>
     <li v-for="(todo,index) in todos" :key="index">
      <p class="task1">{{ todo.task }}</p>
     </li>
   </ul>

  </div>

  <div class="ToDoweek">
 <p>②１週間以内にすることリスト</p>
<p class="weeks">{{weekdo}}</p>

  </div>

  

</div>

</template>

<script>
import HeaderAuth2 from "../components/HeaderAuth2";
export default {

   data() {
    return {

       newtask:"",
       todos:[]
       };
  },

  methods:{
     doAdd1(){
      this.todos.push({
        task:this.newtask
      });
     }
  },
  
  components: {
    HeaderAuth2
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
 font-size: 25px;
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

  

</style>
