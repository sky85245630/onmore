<template>
  <div class="hello">
    <div class="QQ" @click="controlShow('hide')">X</div>
    <h1>{{ tittle }}</h1>
    <h2>{{ des }}</h2>
    <button @click="toCount('count')" class="btnQ">
      {{ dCount }}
    </button>
  </div>
</template>

<script>
// 彈跳視窗
// 設計製作一個寬高各 300px 的彈跳視窗component(不使用任何 ui 框架)
// 簡單使用z-index 999 做出 黑色mask
// 點擊父層一個按鈕顯示出彈跳視窗
// 以父層data變數控制彈跳視窗的顯示與關閉
// 彈跳視窗 compoment 有個關閉(close)按鈕點擊之後可以關閉彈跳視窗

// 彈跳視窗compoment使用 slot 讓使用者可以自訂彈窗的title 與 content

// 彈跳視窗 compoment 內有加法按鈕, 點擊可以讓父層 count變數 +1
// count 變數用store(vuex) 存放
export default {
  name: "dialog",
  props: {
    tittle: String,
    des: String,
    dCount: Number,
  },

  data() {
    return {};
  },
  methods: {
    controlShow(e) {
      this.$emit("childShow", e);
    },
    toCount(e) {
      this.$emit("toCount123", e);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.hello {
  width: 300px;
  height: 300px;
  background-color: pink;
  position: relative;
}

.QQ {
  position: absolute;
  right: 10px;
  top: 10px;
  width: 20px;
  height: 20px;
  border: 1px solid black;
  color: white;
  border-radius: 50%;
}

.btnQ {
  width: 100px;
  height: 40px;
}

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
