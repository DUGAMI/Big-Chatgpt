<template>

    <!-- 不加一个div就会因为flex布局铺满整个row  -->
    <div class="bd-example">

        <div v-for="sentence in getChatContent">
            <div class="alert alert-primary"  style="display: inline-block">
                <p>{{ sentence }}</p>
            </div>
        </div>

    </div>

</template>

<script>

var chat1=["你怎么看日本排放核废水这件事？",
    "根据我截至2021年的知识，日本福岛核事故发生于2011年，这次事故导致了大量放射性废水的产生。自那时以来，日本一直在努力应对这个问题，并采取了一系列措施来处理核废水。然而，近期关于福岛核电站处理核废水的争议再次引起了公众的关注。\n\n 需要指出的是，政府和专家组织应该在做出决策时充分考虑公众的意见和关切，并确保透明度和科学性。对于这个问题的最终解决方案，应该基于严格的科学评估和国际共识，同时确保尽可能最小化潜在的环境和健康风险。",
    "然而有专家认为排放的核废水并没有降低到对环境无害的标准，日本政府这种做法是自私的。",
    "是的，关于福岛核废水排放的问题存在争议和不同意见，包括有专家对日本政府的做法表示质疑。\n\n 需要注意的是，这只是部分专家和活动人士的观点，而并非整个专家界的共识。在这个问题上，存在着不同的意见和立场。最终的决策需要综合考虑多方观点，并以科学和透明的方式进行评估和决策。"]

var chat2=["你好","你好！有什么我可以帮助的吗？","给我表演一下鸡你太美","《鸡你太美》是一首非常流行的中文歌曲，由陈柯宇演唱。作为一款语言模型，我无法进行表演，但我可以提供这首歌的歌词给你。你可以通过搜索引擎或音乐平台找到完整的音乐和演唱。\n" + "这是《鸡你太美》的部分歌词：\n" + "鸡你太美\n" + -"鸡你太美\n" + "鸡你太美\n" + "你的眼睛\n" + "鸡你太美\n" + "鸡你太美"]
var chatList=[chat2,chat1];

export default {
    props:["messageChatIndex"],
    data(){
        return{

        }
    },
    computed:{
        getChatContent()
        {
            return chatList[this.messageChatIndex]
        }
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