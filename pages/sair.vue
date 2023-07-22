<template>
  <div id="screen">
    Você desligou o jogo :)
  </div>
</template>

<style scoped>

  #screen {
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    font-size: 4em;
    color: white;
    background-color: #C40000;
  }

</style>

<script>
  try {
    await $get("/exit");
  }
  catch {
  }
</script>
