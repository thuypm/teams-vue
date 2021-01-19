<template>
  <div>
    <chat-meeting />
    <task-manager/>
    <stream-screen class="stream-screen" />
  </div>
</template>
<script>
import ChatMeeting from "./Meeting/ChatMeeting.vue";
import StreamScreen from "./Meeting/StreamScreen.vue";
import TaskManager from "./Meeting/TaskManager.vue";
export default {
  components: { ChatMeeting, StreamScreen,TaskManager },
};
</script>
<style scoped>
.stream-screen {
  width: calc(100% - 300px);
  width: -webkit-calc(100% - 300px);
  width: -moz-calc(100% - 300px);
  width: -o-calc(100% - 300px);
  width: expression(100% - 300px);
  float: left;
}
</style>