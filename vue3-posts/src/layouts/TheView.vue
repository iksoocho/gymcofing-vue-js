<template>
  <!--
    '/' -> HomeView.vue가 렌더링 되야하고,
    '/about' -> AboutView가 렌더링 되어야 한다.
  -->
  <main>
    <div class="container py-4">
      <RouterView></RouterView>
    </div>
  </main>
</template>

<script>
export default {
  setup() {
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
