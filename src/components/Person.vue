<template>
    <div class="person">
        <h2>品牌：{{ car.brand }}</h2>
        <h2>价格：{{ car.price }}</h2>
        <button @click="changePrice">修改价格</button>
        <button @click="changeCar">修改汽车</button>
        <h2>当前求和：{{ sum }}</h2>
        <button @click="changeSum">sum加1</button>
    </div>
</template>

<script setup lang="ts" name="Person234">
    import {reactive} from 'vue'
    import {ref} from 'vue'

    // let age = reactive(100) //类型“number”的参数不能赋给类型“object”的参数。ts-plugin(2345)
   
    //数据
    let car = reactive({brand:"宝马",price:100})
    console.log(1,car)

    let sum = ref(0)
    //方法
    function changePrice(){
        car.price += 10
    }

    function changeSum(){
        sum.value += 1
    }

    function changeCar(){
        // car = reactive({brand:"奔驰",price:200}) //这样写页面不更新
        Object.assign(car,{brand:"奔驰",price:200}) //这样写页面更新
    }
   



</script>