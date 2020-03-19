<template>
  <div>
    <div class="header-title">
      <div>
        <img src="../assets/flag.png" alt="Japan Flag" />
      </div>
      <h2>Kanji Custom Search</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {};
  }
};
</script>

<!--
 base : hsl(3, 50%, 50%)

 dark : 
 (3, 100%, 70%)

ligth : hsl(3, 50%, 90%)
-->

<style lang="scss">
@import "_variables";
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: hsl(3, 100%, 90%);
}
.header-title {
  display: flex;
  background-color: hsl(3, 100%, 70%);
  margin: 1rem 1rem;
  align-items: center;
  justify-content: start;
  height: 10rem;
  border-radius: 10px;
}
img {
  width: 200px;
  margin: 1rem;
  border-radius: 15px;
}
h2 {
  font-size: 48px;
  font-weight: bold;
  margin-left: 1rem;
  font-family: $kanjiFont;
}
</style>
