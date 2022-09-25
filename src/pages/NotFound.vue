<template>
  <div class="error">
    <div class="code">
      <p>404</p>
    </div>
    <div class="msg-en">
      <p>Page</p>
      <p>Not</p>
      <p>Found</p>
    </div>
  </div>
  <div class="msg-ja">お探しのページは見つかりませんでした。</div>
</template>

<style scoped>
  .error {
    margin-top: 20px;
    display: flex;
    justify-content: center;
    gap: 20px;
  }
  .code {
    font-size: 64px;
    font-weight: bold;
    background-image: linear-gradient(-20deg, #616161 0%, #9bc5c3 100%);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
  .msg-en {
    margin-top: 8px;
  }
  .msg-ja {
    font-size: 18px;
    text-align: center;
  }
</style>