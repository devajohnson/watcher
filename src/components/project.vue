<template>
    <h1>Hai breadcrumbs</h1>
    <div>
        <ul class="breadcrumb">
  <li><a href="#">{{array[0]}}</a></li>
  <li><a href="#"><button @click="change()" class="btn">...</button></a></li>
   <!-- &#8943; -->
   <li><a href="#">{{array[array.length -2]}}</a></li>
    <li><a href="#">{{array[array.length -1]}}</a></li>
</ul>
    </div>
    <div class="crtcode" v-if="content">
      <div>
        <ul>
        <li v-for="string in crtArr" :key="string"><a href="#">{{string}}</a></li>
        </ul>
       </div>
    </div>
</template>
<script>

export default {
 name:'prucess',
 data(){
    return{
      array:['ab','cd','ef','gh','ij','kl','mn','op','qr','st','uv','wx','yz'],
      content:false,
      crtArr:[]
    }
     
 },
 created(){
   this.crtArr=this.array.slice(1,11)
 },
 methods:{
   change(){
     this.content=!this.content
 }
 }
 } 
</script>
<style scoped>
ul.breadcrumb {
  padding: 10px 16px;
  list-style: none;
  background-color: #eee;
}
ul.breadcrumb li {
  display: inline;
  font-size: 18px;
}
ul.breadcrumb li+li:before {
  padding: 8px;
  color: black;
  content: "/\00a0";
}

ul.breadcrumb li a {
  color: #0275d8;
  text-decoration: none;
}
ul.breadcrumb li a:hover {
  color: #01447e;
  text-decoration: underline;
}
.crtcode{
 background-color: lightblue;
  width: 100px;
  height: 100px;
  overflow: auto; 
}

</style>