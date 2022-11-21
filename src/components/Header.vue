<template>
  <div>
    <h1>{{ mainTitle }}</h1>
    <hr />
  </div>
</template>
<script>
export default {
  name: 'Header',
  props: {
    mainTitle: String
  }
}
</script>