<script>
  export let image;
  export let alt;
</script>

<style>
  section {
    position: relative;
    width: 65%;
    height: 100%;
  }

  img {
    width: 100%;
    height: 100%;
  }
</style>

<section>
  <img src={image} {alt} />
</section>

