<template>

    <div class="d-grid gap-2">
        <button class="btn btn-primary" type="button" @click="$emit('switchWindow',{windowName:'FriendList',index:-1})">Bot</button>
    </div>

    <div class="list-group">
        <a v-for="(role,index) in roleList" href="#" class="list-group-item list-group-item-action" :class="{active:index===selectedIndex}" aria-current="true" @click="sendData(index)">
            <div class="d-flex w-100 justify-content-between">
                <h5 class="mb-1">{{ role.name }}</h5>
                <small>{{ role.small }}</small>
            </div>
            <p class="mb-1">{{ role.lastMessage }}</p>
            <small>{{ role.samll2 }}</small>
        </a>

    </div>

</template>

<script>
export default {
    name: "DirectMessage",
    data(){
        return{
            roleList:[{name:"蔡徐坤",small:"3 days ago",lastMessage:"历史消息：鸡你太美 鸡你太美......",samll2:"And some small print."},
                {name:"chat-gpt",small:"3 days ago",lastMessage:"是的，关于福岛核废水排放的问题存在争议和不同意见，包括有......",samll2:"And some small print."},
                {name:"女朋友",small:"3 days ago",lastMessage:"你在干嘛",samll2:"And some small print."}],
            selectedIndex:-1
        }
    },
    methods:{
        //注册事件，上面的是原生事件机制，用来给父组件传递数据，下面的是外部引用事件机制，给兄弟组件传递数据
        sendData(num){
            this.$emit("switchWindow",{windowName:"ChatArea",index:num})
            this.selectedIndex=num
        }
    }
}
</script>