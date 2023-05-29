<script>

import DirectMessage from './components/DirectMessage.vue';
import ChatArea from './components/ChatArea.vue';
import FriendList from './components/FriendList.vue';


export default {
    name: "App",
    components:{
        DirectMessage,ChatArea,FriendList
    },
    data(){
        return{
            leftWindow:'ChatArea',
            chatIndex:-1
        }
    },
    methods:{
        switchWindows(window)
        {
            this.leftWindow=window.windowName
            this.chatIndex=window.index
            console.log("run switchWindows"+window.windowName+" "+window.index)
        }
    }
}

</script>

<template>

    <div class="container-fluid">
        <div class="row" style="height: 100vh">

            <div class="col-3 border border-primary">
                <DirectMessage @switchWindow="switchWindows"></DirectMessage>
            </div>
            <div class="col-9">
                <component :is="leftWindow" :messageChatIndex="chatIndex"></component>
            </div>

        </div>
    </div>


</template>

<style scoped>

</style>
