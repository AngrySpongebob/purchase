<template>
  <div class="purchaseList">
    <table border="1" cellspacing="0">
      <thead>
        <tr>
          <th></th>
          <th>商品名称</th>
          <th>商品单价</th>
          <th>购买数量</th>
          <th>操作</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(shop, index) in list">
          <td>{{index+1}}</td>
          <td>{{shop.name}}</td>
          <td>{{shop.price}}</td>
              <td><button @click="removeHandle(index)" :disabed="shop.count === 1">-</button>{{shop.count}}<button @click="addHandle(index)">+</button></td>
          <td><input type="button" @click="deleteShop(index)" name="" value="移除"></td>
        </tr>
      </tbody>
    </table>
    <p>总价：￥{{totalPrice}}</p>
  </div>
</template>

<script>
export default {
  name: 'purchaseList',
  data () {
    return {
      list:[
        {
          id:1,
          name:"《Tom》",
          price:20.0,
          count:1
        },
        {
          id:2,
          name:"《Jerry》",
          price:20.0,
          count:1
        },
        {
          id:3,
          name:"《Tree》",
          price:20.0,
          count:1
        },
        {
          id:4,
          name:"《Cat》",
          price:20.0,
          count:1
        }
      ]
    }
  },
  computed:{
    totalPrice:function(){
      var totalprice =0
      for(var i of this.list){
        totalprice += i.price*i.count
      }
      return totalprice
    }
  },
  methods:{
    addHandle:function(index){
      this.list[index].count ++;
    },
    removeHandle:function(index){
      if(this.list[index].count === 1) return;
      this.list[index].count --;
    },
    deleteShop:function(index){
      console.log(index)
      this.list.splice(index, 1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2,h3,h4 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
p{
  text-align: left;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
table{
  width:300px;
  padding:10px;
  text-align: center;
  border-collapse: collapse;
}
</style>
