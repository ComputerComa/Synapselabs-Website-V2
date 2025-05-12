<template>
  <SiteNavbar></SiteNavbar>
  <div>

      <NuxtPage />

  </div>
  <SiteFooter></SiteFooter>
</template>

<style lang="css">
body {
  font-family: Arial, sans-serif;

  background-color: dimgray;
  display: flex;
  min-height: 100vh;
  width: 100%;
}

header {
  min-height: 50px;
}

footer {
  min-height: 50px;
}


.page-enter-active,
.page-leave-active {
  transition: all 0.4s;
}
.page-enter-from,
.page-leave-to {
  opacity: 0;
  filter: blur(1rem);
}

body {
  display: flex;
  flex-direction: column;
}

main {
  flex: 1;
}

</style>
