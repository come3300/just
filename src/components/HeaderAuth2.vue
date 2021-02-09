<template>
<div class="HeaderTodo">
  <p>Just Do it.</p>
  
</div>
</template>

<style scoped>
.HeaderTodo{
  background: #fda634;
  height: 70px;
  width: 100%;
  margin : 5px auto;
  padding : 10px;
  
}

.HeaderTodo p{
  color: #f8f8f8;
  font-size: 40px;
  font-weight: bold;
}

@media screen and (max-width : 480px){
  .HeaderTodo{
    width: 100%;
    float: none;
    overflow: hidden;
    margin-bottom: 0;
    height: 10%;
  }
  .HeaderTodo p{
     font-size: 100px;
  }
}

@media screen and (max-width : 768px){
  .HeaderTodo p{
  color: #f8f8f8;
  font-size: 30px;
  font-weight: bold;
  white-space: nowrap;
  margin: 0;
}


}

</style>