<template>
  <div class="modal" @click="$emit('close')">
    <div class="inner">
      <div class="message" v-if="success">
        <img src="@/assets/img/me.svg" alt="lovely">
        <p>Congratulation! You've pooped!</p>
      </div>
      <div class="message" v-else>
        <img src="@/assets/img/sorry.svg" alt="">
        <p>We're very sorry that you didn't poop...</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['success']
}
</script>

<style scoped>
img {
  height: 50px;
  width: 50px;
}
.message {
  display: flex;
  grid-gap: 10px;
  align-items: center;
}
.modal {
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(0, 0, 0, 0.517);
}
.inner {
  background-color: white;
  border-radius: 20px;
  padding: 10px;
  box-shadow: 0 0 20px 0px #0000004a;
}
</style>