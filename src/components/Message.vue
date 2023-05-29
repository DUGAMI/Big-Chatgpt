<template>
    <!-- 不加一个div就会因为flex布局铺满整个row  -->
    <div class="bd-example">

        <div v-for="sentence in chatContent">
            <div class="alert alert-primary"  style="display: inline-block">
                <p>{{ sentence }}</p>
            </div>
        </div>

    </div>

</template>

<script>

import mitter from '../main.js'
export default {
    name: "message",
    data(){
        return{
            chatContent:[]
        }
    },
    methods:{
        //接受到事件后，把chatContent写入data里，这样就能在数据改变时直接有响应了
        register(){
            mitter.on("switch",(e)=>{this.chatContent=e})
        }
    },
    //订阅事件，其实可以把register里的内容直接写到mounted里
    mounted() {
        console.log("Message loading end")
        this.register()
    }
}
</script>

<style scoped>
    .bd-example {
        padding: 1.5rem;
        margin-right: 0;
        margin-left: 0;
        border-width: 1px;
        border-top-left-radius: 0.25rem;
        border-top-right-radius: 0.25rem;
    }
</style>