<template>
  <div class="home">
    <header>
      <p>PoopCounter</p>
    </header>
    <div class="content">
      <div class="left">
        <p>Did you poop?</p>
        <div class="answers">
          <div class="yes" @click="addPoop">
            <img src="@/assets/img/poop.svg" alt="poop">
            <p>Yes!</p>
          </div>
          <div class="no" @click="noPoop">
            <img src="@/assets/img/no.svg" alt="nopoop">
            <p>No...</p>
          </div>
        </div>
      </div>
      <div class="right">
        <p>Your poop count is...</p>
        <div class="count">
          <p>{{ count }}</p>
        </div>
      </div>
    </div>
    <footer>
      <p class="names">made by Lina and Danya</p>
      <div class="emails">
        <a href = "mailto:linatolmach@gmail.com">linatolmach@gmail.com</a>
        <a href = "mailto:ddanili56@gmail.com">ddanili56@gmail.com</a>
      </div>
    </footer>
    <Modal v-if="showModal" @close="showModal = false" :success="success"></Modal>
  </div>
</template>

<script>
  import Modal from '@/components/Modal.vue'
 export default {
  components: {
    Modal
  },
  data() {
    return {
      count: 0,
      showModal: false,
      success: true
    }
  },
  methods: {
    addPoop() {
      this.count++;
      localStorage.setItem('count', this.count.toString());
      this.showModal = true;
      this.success = true;
    },
    noPoop() {
      this.showModal = true;
      this.success = false;
    }
  },
  mounted() {
    this.count = localStorage.getItem('count');
  }
 }
</script>
