<script>

import Message from './Message.vue';
import InputArea from'./InputArea.vue';

export default {
    name: "ChatArea",
    components:{
        Message,InputArea
    }
}
</script>

<template>

    <div class="row h-75">
        <Message></Message>
    </div>
    <div class="row h-25 border border-primary">
        <InputArea></InputArea>
    </div>

</template>