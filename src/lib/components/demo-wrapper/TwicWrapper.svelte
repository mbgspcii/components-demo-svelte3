<script>
  import { default as TwicHeader } from './TwicHeader.svelte';
</script>

<div id="twic-demo-wrapper" class="">
  <TwicHeader />
  <main id="twic-demo-container">
    <slot />
  </main>
</div>

<style lang="scss">
  #twic-demo-wrapper {
    & #twic-demo-container {
      margin: 40px;
      max-width: 1500px;
    }
  }

  #twic-demo-wrapper {
    & #twic-demo-container {
      @media screen and (min-width: 768px) {
        margin: 80px 60px;
      }
      @media screen and (min-width: 1600px) {
        margin: 2rem auto;
      }
    }
  }
</style>
