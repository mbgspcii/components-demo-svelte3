<script>
  import TwicAbstract from './components/demo-wrapper/TwicAbstract.svelte';
  import TwicWrapper from './components/demo-wrapper/TwicWrapper.svelte';
  import { TwicImg } from '@twicpics/components/svelte3';

  const verticalConfig = [
    {
      anchor: `center`
    },
    {
      anchor: `top`
    },
    {
      anchor: `bottom`
    }
  ];

  const horizontalConfig = [
    {
      anchor: `center`
    },
    {
      anchor: `left`
    },
    {
      anchor: `right`
    }
  ];

  let indiceConfig = 0;

  $: actualHorizontal = horizontalConfig[indiceConfig];
  $: actualVertical = verticalConfig[indiceConfig];
</script>

<TwicWrapper
  gitHubUrl="https://github.com/TwicPics/components-demo-svelte3/blob/main/src/lib/TwicAnchor.svelte"
>
  <div class="twic-anchor-container">
    <TwicAbstract
      title="anchor property"
      codeSandBoxUrl="https://codesandbox.io/p/github/TwicPics/components-demo-svelte3/main?file=%2Fsrc%2Flib%2FTwicAnchor.svelte&hidenavigation=1"
      codeSandBoxName="TwicPics x Svelte - Anchor property"
    >
      <p>
        <strong>
          The <dfn title="anchor property">anchor</dfn> property positions the image in both
          <span class="twic-code">contain</span>
          and <span class="twic-code">cover</span> mode.
        </strong>
      </p>
      <p>
        Accepted values are <span class="twic-code">top</span>,
        <span class="twic-code">bottom</span>, <span class="twic-code">left</span>,
        <span class="twic-code">right</span>, <span class="twic-code">top-left</span>,
        <span class="twic-code">top-right</span>, <span class="twic-code">bottom-left</span> and
        <span class="twic-code">bottom-right</span>.
      </p>
      <p>For a more specific positionning see:</p>
      <ul>
        <li>
          <a href="/position" title="Home">position</a> property in
          <span class="twic-code">contain</span> mode
        </li>
        <li>
          <a href="/focus" title="Home">focus</a> property in <span class="twic-code">cover</span> mode
        </li>
      </ul>
    </TwicAbstract>
    <div class="twic-testing-container">
      <button
        class="twic-button"
        on:click={() => (indiceConfig = (indiceConfig + 1) % horizontalConfig.length)}
      >
        Click to see anchor effect
      </button>
    </div>
    <div class="twic-grid">
      <div class="twic-item">
        <TwicImg src="cat_1x1.jpg" anchor={actualHorizontal.anchor} mode="cover" ratio="3/4" />
        <span>
          <span>
            <span class="twic-code">anchor="{actualHorizontal.anchor}"</span>
            <span class="twic-code">mode="cover"</span>
          </span>
        </span>
      </div>
      <div class="twic-item">
        <TwicImg src="cat_1x1.jpg" anchor={actualVertical.anchor} mode="cover" ratio="4/3" />
        <span>
          <span>
            <span>
              <span class="twic-code">anchor="{actualVertical.anchor}"</span>
              <span class="twic-code">mode="cover"</span>
            </span>
          </span>
        </span>
      </div>
      <div class="twic-item">
        <TwicImg src="cat_1x1.jpg" anchor={actualHorizontal.anchor} mode="contain" ratio="4/3" />
        <span>
          <span>
            <span class="twic-code">anchor="{actualHorizontal.anchor}"</span>
            <span class="twic-code">mode="contain"</span>
          </span>
        </span>
      </div>
      <div class="twic-item">
        <TwicImg src="cat_1x1.jpg" anchor={actualVertical.anchor} mode="contain" ratio="3/4" />
        <span>
          <span>
            <span>
              <span class="twic-code">anchor="{actualVertical.anchor}"</span>
              <span class="twic-code">mode="contain"</span>
            </span>
          </span>
        </span>
      </div>
    </div>
  </div>
</TwicWrapper>

<style lang="scss">
  .twic-anchor-container {
    :global(.twic-item .twic-w) {
      background-color: #00ffa3;
      display: block;
    }
  }
</style>
