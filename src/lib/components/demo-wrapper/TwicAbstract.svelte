<script>
  export let title;
  export let codeSandBoxUrl = undefined;
  
  let href = undefined;
  const CODESANDBOX = `https://codesandbox.io/p/github/TwicPics/components-demo-svelte3/main?file=`;

  $: if (codeSandBoxUrl) {
    href = `${CODESANDBOX}${codeSandBoxUrl}`;
  }
</script>

<div class="twic-abstract">
  <h1>{title}</h1>
  <div>
    <div>
      <slot />
    </div>
    {#if href}
      <div class="codesandbox-container">
        <a {href} target="_blank" rel="noreferrer">
          <img
            src="https://codesandbox.io/static/img/play-codesandbox.svg"
            alt="Edit on CodeSandbox"
          />
        </a>
      </div>
    {/if}
  </div>
</div>

<style lang="scss">
  .twic-abstract {
    /* margin: 0 0 2rem; */
    margin-bottom: 40px;

    & h1 {
      margin-bottom: 1rem;
    }

    & > div {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      row-gap: 1rem;
      column-gap: 1rem;
      align-items: center;
    }

    & :global(p) {
      margin-bottom: 0.5rem;
      text-align: justify;
    }

    & :global(ul) {
      display: flex;
      flex-direction: column;
      gap: 6px;
      margin: 10px 0;
      padding-left: 32px;
    }

    & a {
      &:link,
      &:visited,
      &:hover,
      &:active {
        color: #8e08fd;
      }
    }
  }
</style>
