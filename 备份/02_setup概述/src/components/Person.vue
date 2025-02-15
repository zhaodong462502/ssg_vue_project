<template>
    <div class="person">
        <h2>姓名：{{ name }}</h2>
        <h2>年龄：{{ age }}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="showTel">查看手机号</button>
    </div>
</template>
<script lang="ts">
    export default {
        name: 'Person',
        beforeCreate() {
            console.log("beforeCreate this is",this)
        },
        setup() {

            console.log("setup this is",this)   
            //数据
            let name = "张三" //此时name 不是一个响应式数据
            let age = 18
            let tel = "12345678901"

            //方法
            function changeName() {
                console.log(1)
                name = "李四"
                console.log(name)
            }
            function changeAge() {
                console.log(2)

                age +=1
                console.log(age)
            }
            function showTel() {
                console.log(3)

                alert(tel)
                console.log(tel)
            }
            return {name:name,age:age,tel:tel,changeName,changeAge,showTel}

            
        },
    }
</script>