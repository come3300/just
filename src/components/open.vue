<template>
<div class="detail">
  <div class="buttonset">
    <p>詳細記入</p>
    <input class="detailinput" type="text" v-model="newdetail" placeholder="5つに細分化">
    <button v-on:click="detaildo">作成</button>
    <button @click="$emit('close')">閉じる</button>
  </div>
  <div class="open">
    <ul>
    <li v-for="(detail,index) in details" :key="index">
       <input type ="checkbox" v-model="index[doit]">
    <p input type="checkbox" v-bind="details"
    class="detailcheck">
    {{detail.doit}}
    </p>
    </li>
    </ul>
  </div>
</div>

</template>



<script>
export default {
  data() {
    return {
      props:["close"],
      newdetail:"",
      details:[]
    };
  },
  methods: {
    detaildo(){
     this.details.push({
   doit:this.newdetail
     });
     this.newdetail="";
    },

    sendParent() {
      this.$emit("del");
    }
  }
};
</script>

<style scoped>
.detail{
  z-index:1;
  position:fixed;
  top:0;
  left:0;
  width:100%;
  height:100%;
  background-color:rgba(0, 0, 0, 0.2);
  align-items: center;
  justify-content: center;
  color: black;
}

.detailinput{
color: #000;
}

.buttonset{
  position: relative;
  left: 40%;
}

.open{
    box-sizing: border-box;
    cursor: pointer;
    display: inline-block;
    padding: 5px 30px;
    position: relative;
    width: auto;
    vertical-align:middle;
    left: 35%;
}

.detailcheck{
  top: 10%;
}

ul{
  list-style: none;
  color:black;
  vertical-align:middle;
   }

li{
  width: 95%;
  height: 70px;
  border: 3px solid #fda634;
  color: black;
  margin: 5px;
  }

  
</style>