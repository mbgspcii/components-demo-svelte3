<script>
  import TwicAbstract from './components/demo-wrapper/TwicAbstract.svelte';
  import TwicWrapper from './components/demo-wrapper/TwicWrapper.svelte';
  import Code from './components/Code.svelte';
  import { TwicImg } from '@twicpics/components/svelte3';

  const imgUrl = `components/woman-and-winter.jpg`;
  const ratioValues = [`2.39`, `16/9`, `4/3`, ``, `0.75`];
  let ratioIndex = 0;
  let fullWidthAera = true;

  const onChangeRatio = () => {
    ratioIndex = (ratioIndex + 1) % ratioValues.length;
  };

  const onChangeAreaWidth = () => {
    fullWidthAera = !fullWidthAera;
  };
</script>

<!-- demonstrates ratio features -->
<TwicWrapper gitHubUrl="src/lib/TwicRatio.svelte">
  <div class="twic-ratio-container">
    <TwicAbstract title="ratio property" codeSandBoxUrl="src/lib/TwicRatio.svelte">
      <p>
        <strong>
          The <dfn>ratio</dfn> property determines the value of the width/height ratio of the image display
          area.
        </strong>
      </p>
      <p>Its value can be:</p>
      <ul>
        <li>
          a ratio expression of the form width/height like
          <Code>4/3</Code>,
          <Code>16/9</Code>, or
          <Code>1/1</Code>.
        </li>
        <li>
          a number that is the result of such an expression like
          <Code>1.85</Code>,
          <Code>2</Code>, or
          <Code>0.5</Code>.
        </li>
      </ul>
      <p>
        A square area (<Code>ratio="1"</Code>) will be created by default.
      </p>
    </TwicAbstract>
    <div class="twic-testing-container">
      <button class="twic-button" on:click={onChangeRatio}>
        Click to change the aspect-ratio
      </button>
      <button class="twic-button" on:click={onChangeAreaWidth}>
        Click to change the area width
      </button>
    </div>
    <div class="twic-grid" class:half-width={fullWidthAera === false}>
      <div class="twic-item">
        <TwicImg src={imgUrl} ratio={ratioValues[ratioIndex]} />
        <span>
          <span class="twic-code"
            >ratio="{ratioValues[ratioIndex] ? ratioValues[ratioIndex] : 1}"</span
          >
          {#if !ratioValues[ratioIndex]}
            - default ratio
          {/if}
          (mode is <Code>cover</Code>)
        </span>
      </div>
      <div class="twic-item">
        <TwicImg src={imgUrl} mode="contain" ratio={ratioValues[ratioIndex]} />
        <span>
          <span class="twic-code"
            >ratio="{ratioValues[ratioIndex] ? ratioValues[ratioIndex] : 1}"</span
          >
          {#if !ratioValues[ratioIndex]}
            - default ratio
          {/if}
          (mode is <Code>contain</Code>)
        </span>
      </div>
    </div>
  </div>
</TwicWrapper>

<style lang="scss">
  .twic-ratio-container {
    .twic-grid {
      --twic-grid-columns-width: 40%;
      &.full-width {
        .twic-item {
          width: 100%;
        }
      }

      &.half-width {
        .twic-item {
          width: 50%;
          margin: auto;
        }
      }
    }

    :global(.twic-item .twic-w) {
      background-color: #00ffa3;
      display: block;
    }
  }
</style>
