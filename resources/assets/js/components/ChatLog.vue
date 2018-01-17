<template lang="html">
    <div class="chat-log">

        <chat-message v-for="message in messages" :message="message"></chat-message>
        <div class="empty" v-show="messages.length ===0">
            Nothing here yet!
        </div>
    </div>
</template>

<script>
    export default {
       props: ['messages']
    }
</script>
<style lang="css">
    .chat-log {
        border: 1px solid #d6daf1;
        margin: 2px;

    }
    .chat-message {
        padding:20px;
        background-color: white;
    }

    .chat-message small {
        color: #38ceff;
        font-weight: 500;
    }
 .chat-log .chat-message:nth-child(even) {
     background-color: #ccc;

 }
    .chat-log .chat-message:nth-child(even) small {
        color: #d5172f;
    }
</style>