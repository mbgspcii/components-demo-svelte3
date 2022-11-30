<script>
  import TwicAbstract from './components/demo-wrapper/TwicAbstract.svelte';
  import TwicWrapper from './components/demo-wrapper/TwicWrapper.svelte';
  import { TwicImg } from '@twicpics/components/svelte3';

  const imgUrl = `components/fox.jpg`;
  const modeValues = [`cover`, `contain`];
  let modeIndex = 0;

  $: finalImgUrl = `${imgUrl}?${modeIndex}`; // trick to force image reload

  const onChangeMode = () => {
    modeIndex = (modeIndex + 1) % modeValues.length;
  };
</script>

<!-- demonstrates mode features (contain or cover) -->
<TwicWrapper gitHubUrl="src/lib/TwicMode.svelte">
  <div class="twic-mode-container">
    <TwicAbstract title="mode property" codeSandBoxUrl="src/lib/TwicMode.svelte">
      <p>
        <strong>
          The
          <dfn>mode</dfn>
          property determines if the image fills or sits inside the area.
        </strong>
      </p>
      <p>Here are the two accepted values:</p>
      <ul>
        <li>
          <span class="twic-code">cover</span>:
          <span> the image fills the area and is cropped accordingly.</span>
        </li>
        <li>
          <span class="twic-code">contain</span>:
          <span> the image sits inside the area with no cropping.</span>
        </li>
      </ul>
    </TwicAbstract>
    <div class="twic-grid">
      <div class="twic-item">
        <button class="twic-button" on:click={onChangeMode}>
          Click to change the mode value
        </button>
        <TwicImg src={finalImgUrl} mode={modeValues[modeIndex]} />
        <span>
          <span class="twic-code">mode="{modeValues[modeIndex]}"</span>
        </span>
      </div>
      <div class="twic-item">
        <TwicImg src={imgUrl} />
        <span>No mode set (<span class="twic-code">cover</span> by default)</span>
      </div>
      <div class="twic-item">
        <TwicImg src={imgUrl} mode="cover" />
        <span>
          <span class="twic-code">mode="cover"</span>
        </span>
      </div>
      <div class="twic-item">
        <TwicImg src={imgUrl} mode="contain" />
        <span>
          <span class="twic-code">mode="contain"</span>
        </span>
      </div>
    </div>
  </div>
</TwicWrapper>

<style lang="scss">
  .twic-mode-container {
    :global(.twic-item .twic-w) {
      background-color: #00ffa3;
      display: block;
    }
  }
</style>
