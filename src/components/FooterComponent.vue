<template>
  <footer>
    <div text-center>
      Found {{len}} characters
    </div>
  </footer>
</template>

<script>
export default {
name: 'FooterComponent',
props: {
  len: Number
}
}
</script>

<style>

</style>