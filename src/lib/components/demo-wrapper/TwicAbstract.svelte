<script>
  export let title;
  export let codeSandBoxName = ``;
  export let codeSandBoxUrl = ``;

  const alt = codeSandBoxName ? ` Edit ${codeSandBoxName} ` : ` Edit on CodeSandbox`;
  const href = `${codeSandBoxUrl}?fontsize=14&hidenavigation=1&theme=dark`;
</script>

<div class="twic-abstract">
  <h1>{title}</h1>
  <div>
    <div>
      <slot />
    </div>
    {#if codeSandBoxUrl}
      <div class="codesandbox-container">
        <a {href}>
          <img src="https://codesandbox.io/static/img/play-codesandbox.svg" {alt} />
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
