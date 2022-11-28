<script>
  import TwicRatio from './TwicRatio.svelte';
  import TwicAbstract from './components/demo-wrapper/TwicAbstract.svelte';
  import TwicWrapper from './components/demo-wrapper/TwicWrapper.svelte';
  import { TwicImg } from '@twicpics/components/svelte3';

  const containSample = [
    {
      anchor: `top`,
      mode: `contain`,
      ratio: `3/4`
    },
    {
      anchor: `bottom`,
      mode: `contain`,
      ratio: `3/4`
    },
    {
      anchor: `left`,
      mode: `contain`,
      ratio: `4/3`
    },
    {
      anchor: `right`,
      mode: `contain`,
      ratio: `4/3`
    }
  ];

  const coverSample = [
    {
      anchor: `left`,
      mode: `cover`,
      ratio: `3/4`
    },
    {
      anchor: `right`,
      mode: `cover`,
      ratio: `3/4`
    },
    {
      anchor: `top`,
      mode: `cover`,
      ratio: `16/9`
    },
    {
      anchor: `bottom`,
      mode: `cover`,
      ratio: `16/9`
    }
  ];
  let indiceConfig = 0;

  $: actualContain = containSample[indiceConfig];
  $: actualCover = coverSample[indiceConfig];
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
        <span class="twic-code">anchor</span> property positions the image <strong>in both</strong>
        <span class="twic-code">contain</span>
        and <span class="twic-code">cover</span> mode.
      </p>
      <p>
        Accepted values are <span class="twic-code">top</span>,
        <span class="twic-code">bottom</span>, <span class="twic-code">left</span>,
        <span class="twic-code">right</span>, <span class="twic-code">top-left</span>,
        <span class="twic-code">top-right</span>, <span class="twic-code">bottom-left</span> and
        <span class="twic-code">bottom-right</span>.
      </p>
    </TwicAbstract>
    <div class="twic-testing-container">
      <button
        class="twic-button"
        on:click={() => (indiceConfig = (indiceConfig + 1) % coverSample.length)}
      >
        Click to see anchor effect
      </button>
    </div>
    <div class="twic-grid">
      <div class="twic-item">
        <TwicImg
          src="cat_1x1.jpg"
          mode={actualCover.mode}
          ratio={actualCover.ratio}
          anchor={actualCover.anchor}
        />
        <span>
          <span>
            <span class="twic-code">anchor="{actualCover.anchor}"</span>
            <span class="twic-code">mode="{actualCover.mode}"</span>
            <span class="twic-code">ratio="{actualCover.ratio}"</span>
          </span>
        </span>
      </div>
      <div class="twic-item">
        <TwicImg src="cat_1x1.jpg" mode={actualCover.mode} ratio={actualCover.ratio} />
        <span>No anchor set (<span class="twic-code"> center</span> by default)</span>
      </div>
      <div class="twic-item">
        <TwicImg
          src="cat_1x1.jpg"
          mode={actualContain.mode}
          ratio={actualContain.ratio}
          anchor={actualContain.anchor}
        />
        <span>
          <span>
            <span class="twic-code">anchor="{actualContain.anchor}"</span>
            <span class="twic-code">mode="{actualContain.mode}"</span>
            <span class="twic-code">ratio="{actualContain.ratio}"</span>
          </span>
        </span>
      </div>
      <div class="twic-item">
        <TwicImg src="cat_1x1.jpg" mode={actualContain.mode} ratio={actualContain.ratio} />
        <span>No anchor set (<span class="twic-code"> center</span> by default)</span>
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
