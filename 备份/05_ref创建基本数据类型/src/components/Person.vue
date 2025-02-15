<template>
    <div class="person">
        <h2>姓名：{{ name }}</h2>
        <h2>年龄：{{ age }}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="showTel">查看手机号</button>
       
    </div>
</template>

<script setup lang="ts" name="Person234">
    import {ref} from 'vue'
    let name = ref("张三") //此时name 不是一个响应式数据
    let age = ref(18)
    let tel = "12345678901"
    // let x = d   //d无法在setup中使用

    //方法
    function changeName() {
        console.log(1)
        name.value = "李四"
        console.log(name.value)
    }
    function changeAge() {
        console.log(2)

        age.value +=1
        console.log(age.value)
    }
    function showTel() {
        console.log(3)

        alert(tel)
        console.log(tel)
    }
</script>