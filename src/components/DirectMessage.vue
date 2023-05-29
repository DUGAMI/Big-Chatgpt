<template>

    <div class="d-grid gap-2">
        <button class="btn btn-primary" type="button" @click="$emit('intoFriend','FriendList')">Friend</button>
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

import emitter from '../main.js'

var chat1=["你怎么看日本排放核废水这件事？",
    "根据我截至2021年的知识，日本福岛核事故发生于2011年，这次事故导致了大量放射性废水的产生。自那时以来，日本一直在努力应对这个问题，并采取了一系列措施来处理核废水。然而，近期关于福岛核电站处理核废水的争议再次引起了公众的关注。\n\n 需要指出的是，政府和专家组织应该在做出决策时充分考虑公众的意见和关切，并确保透明度和科学性。对于这个问题的最终解决方案，应该基于严格的科学评估和国际共识，同时确保尽可能最小化潜在的环境和健康风险。",
    "然而有专家认为排放的核废水并没有降低到对环境无害的标准，日本政府这种做法是自私的。",
    "是的，关于福岛核废水排放的问题存在争议和不同意见，包括有专家对日本政府的做法表示质疑。\n\n 需要注意的是，这只是部分专家和活动人士的观点，而并非整个专家界的共识。在这个问题上，存在着不同的意见和立场。最终的决策需要综合考虑多方观点，并以科学和透明的方式进行评估和决策。"]

var chat2=["你好","你好！有什么我可以帮助的吗？","给我表演一下鸡你太美","《鸡你太美》是一首非常流行的中文歌曲，由陈柯宇演唱。作为一款语言模型，我无法进行表演，但我可以提供这首歌的歌词给你。你可以通过搜索引擎或音乐平台找到完整的音乐和演唱。\n" + "这是《鸡你太美》的部分歌词：\n" + "鸡你太美\n" + -"鸡你太美\n" + "鸡你太美\n" + "你的眼睛\n" + "鸡你太美\n" + "鸡你太美"]
var chatList=[chat1,chat2];

export default {
    name: "DirectMessage",
    data(){
        return{
            roleList:[{name:"蔡徐坤",small:"3 days ago",lastMessage:"历史消息：鸡你太美 鸡你太美......",samll2:"And some small print."},
                {name:"chat-gpt",small:"3 days ago",lastMessage:"是的，关于福岛核废水排放的问题存在争议和不同意见，包括有......",samll2:"And some small print."},
                {name:"女朋友",small:"3 days ago",lastMessage:"你说的对，但是原神是一款......",samll2:"And some small print."}],
            selectedIndex:-1
        }
    },
    methods:{
        //注册事件，上面的是原生事件机制，用来给父组件传递数据，下面的是外部引用事件机制，给兄弟组件传递数据
        sendData(num){
            this.$emit("intoFriend","ChatArea")
            this.selectedIndex=num

            emitter.emit("switch",chatList[num])
            console.log("end emit")
        }
    }
}
</script>