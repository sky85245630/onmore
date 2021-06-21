<template>
  <div class="home">
    <button @click="showDialog">彈窗</button>

    <Dialog
      v-if="isShow"
      tittle="標題"
      des="內容"
      :dCount="count"
      @childShow="isShow = false"
      @toCount123="countF()"
    />
  </div>
</template>

<script>
// @ is an alias to /src
import Dialog from "@/components/dialog.vue";

export default {
  name: "Home",
  components: {
    Dialog,
  },
  watch: {
    isShow: {
      handler() {},
    },
  },
  data() {
    return {
      isShow: false,
      count: 0,
    };
  },
  methods: {
    showDialog() {
      this.isShow = !this.isShow;
    },
    countF() {
      const vm = this;
      vm.count++;
      // vm.$store.commit("storeToVuex", this.isShow);
    },
  },
};
</script>

<style lang="css"></style>
