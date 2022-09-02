<template>
  <div class="cardBox">
    <div class="container tasker">
      <h2>Today is:</h2>
      <h2>{{ getCurrentDate }}</h2>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CurrentTime',
  computed: {
    getCurrentDate() {
      const browserLocale = navigator.language && navigator.languages.length
        ? navigator.languages[0]
        : navigator.language;

      const intlDateTime = new Intl.DateTimeFormat(browserLocale, {
        year: 'numeric',
        month: 'numeric',
        day: 'numeric',
        hour: 'numeric',
        minute: 'numeric',
      });
      return intlDateTime.format(new Date());
    },
  },
};
</script>
<style scoped>
.tasker {
  margin: 20px;
}
</style>
