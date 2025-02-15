<template>
    <div class="person">
        <h2>品牌：{{ car.brand }}</h2>
        <h2>价格：{{ car.price }}</h2>
        <button @click="changePrice">修改价格</button>
       <h2>游戏列表</h2>
       <ul>
           <li v-for="game in games" :key="game.id">{{game.name}}</li>
         </ul>
         <button @click="changeFirstGameName">修改第一个游戏名称</button>

        <h2>obj信息：{{obj.a.b.c}}</h2>
        <button @click="changeObj">修改obj</button>
    </div>
</template>

<script setup lang="ts" name="Person234">
    import {reactive} from 'vue'
    import {ref} from 'vue'

    // let age = reactive(100) //类型“number”的参数不能赋给类型“object”的参数。ts-plugin(2345)
   
    //数据
    let car = reactive({brand:"宝马",price:100})
    console.log(1,car)

    let games = reactive([
        {id:1,name:"王者荣耀"},
        {id:2,name:"英雄联盟"},
        {id:3,name:"绝地求生"},
    ])

    let obj = reactive({
        a:{
            b:{
                c:666
            }
        }
    })
    //方法
    function changePrice(){
        car.price += 10
    }
    function changeFirstGameName(){
        games[0].name = "王者荣耀2"
    }

    function changeObj(){
        obj.a.b.c += 10
    }


</script>