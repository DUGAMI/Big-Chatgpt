<template>

    <div class="list-group">

        <a v-for="bot in botList" href="#" class="list-group-item list-group-item-action" aria-current="true" @click="$emit('switchWindow',{windowName:'BotSetup',index:-1})">
            <div class="d-flex w-100 justify-content-between">
                <h5 class="mb-1">{{ bot.name }}</h5>
                <small>{{ bot.small }}</small>
            </div>
            <p class="mb-1">{{ bot.lastMessage }}</p>
            <small>{{ bot.samll2 }}</small>
        </a>

        <a href="#" class="list-group-item list-group-item-action" aria-current="true" @click="$emit('switchWindow',{windowName:'ChatRoom',index:-1})">
            <div class="d-flex w-100 justify-content-between">
                <h5 class="mb-1">聊天室</h5>
                <small>3 days ago</small>
            </div>
            <p class="mb-1"></p>
            <small>And some small print.</small>
        </a>

    </div>


</template>

<script>

export default {
    name: "FriendList",
    data() {
        return {
            botList: [{
                name: "蔡徐坤",
                small: "3 days ago",
                lastMessage: "历史消息：鸡你太美 鸡你太美......",
                samll2: "And some small print."
            },
                {
                    name: "chat-gpt",
                    small: "3 days ago",
                    lastMessage: "是的，关于福岛核废水排放的问题存在争议和不同意见，包括有......",
                    samll2: "And some small print."
                },
                {
                    name: "女朋友",
                    small: "3 days ago",
                    lastMessage: "你在干嘛",
                    samll2: "And some small print."
                }],
            selectedIndex: -1
        }
    }
}
</script>

<style scoped>

</style>