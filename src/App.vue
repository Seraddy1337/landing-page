<template>
  <div id="app">
    <Content />
  </div>
</template>

<script>
import Content from './components/Content.vue'

export default {
  name: 'App',
  components: {
    Content
  }
};
(function () {
    function setRootFontSize() {
        let rem, rootWidth;
        let rootHtml = document.documentElement;
        //限制展现页面的最小宽度
        rootWidth = rootHtml.clientWidth < 768 ? 768 : rootHtml.clientWidth;
        rem = rootWidth / 1366 * 16;
        // 动态写入样式
        rootHtml.style.fontSize = `${rem}px`;
    }
    setRootFontSize();
    window.addEventListener("resize", setRootFontSize, false);
})();
</script>

<style>
  html, body {
    margin: 0;
  }
</style>
