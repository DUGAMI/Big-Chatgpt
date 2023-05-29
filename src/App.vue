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
            leftWindow:'ChatArea'
        }
    },
    methods:{
        intoFriend(window)
        {
            this.leftWindow=window
        }
    }
}

</script>

<template>

    <div class="container-fluid">
        <div class="row" style="height: 100vh">

            <div class="col-3 border border-primary">
                <DirectMessage @intoFriend="intoFriend"></DirectMessage>
            </div>
            <div class="col-9">
                <component :is="leftWindow"></component>
            </div>

        </div>
    </div>


</template>

<style scoped>

</style>
