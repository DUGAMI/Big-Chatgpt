<script>

import Message from './Message.vue';
import InputArea from'./InputArea.vue';

export default {
    name: "ChatArea",
    props:["messageChatIndex"],
    components:{
        Message,InputArea
    }
}
</script>

<template>

    <div class="row h-75">
        <Message :messageChatIndex="messageChatIndex"></Message>
    </div>
    <div class="row h-25 border border-primary">
        <InputArea></InputArea>
    </div>

</template>