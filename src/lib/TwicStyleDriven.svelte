<script>
  import TwicAbstract from './components/demo-wrapper/TwicAbstract.svelte';
  import TwicWrapper from './components/demo-wrapper/TwicWrapper.svelte';
  import Code from './components/Code.svelte';
  import { TwicImg } from '@twicpics/components/svelte3';

  const imgUrl = `components/horse.jpg`;
</script>

<div id="twic-style-driven-container">
  <TwicWrapper gitHubUrl="src/lib/TwicStyleDriven.svelte">
    <TwicAbstract title="CSS style driven" codeSandBoxUrl="src/lib/TwicStyleDriven.svelte">
      <p>You can set up the TwicPics components using pure CSS and the power of CSS variables.</p>
    </TwicAbstract>
    <h2>1. Display ratio with <Code>--twic-ratio</Code></h2>
    <div class="twic-grid">
      <div class="twic-item landscape">
        <TwicImg src={imgUrl} />
        <span
          >class
          <Code>landscape</Code>
        </span>
      </div>
      <div class="twic-item square">
        <TwicImg src={imgUrl} />
        <span
          >class
          <Code>square</Code>
        </span>
      </div>
      <div class="twic-item portrait">
        <TwicImg src={imgUrl} />
        <span
          >class
          <Code>portrait</Code>
        </span>
      </div>
    </div>
    <h2>
      2. Class combination: <Code>object-fit</Code> and
      <Code>position</Code> with
      <Code>--twic-mode</Code> and
      <Code>twic-position</Code>
    </h2>
    <div class="twic-grid">
      <div class="twic-item contain left">
        <TwicImg src={imgUrl} ratio="16/9" />
        <span
          >class
          <Code>contain</Code>
          & class
          <Code>left</Code>
        </span>
      </div>
      <div class="twic-item contain right">
        <TwicImg src={imgUrl} ratio="16/9" />
        <span
          >class
          <Code>contain</Code>
          & class
          <Code>right</Code>
        </span>
      </div>
      <div class="twic-item cover">
        <TwicImg src={imgUrl} focus="50px100p" ratio="16/9" />
        <span
          >class
          <Code>cover</Code>
        </span>
      </div>
    </div>
    <h2>
      3. Other classical settings (here with
      <Code>width</Code>)
    </h2>
    <div class="twic-grid">
      <div class="twic-item lg">
        <TwicImg src={imgUrl} />
        <span
          >class
          <Code>lg</Code>
        </span>
      </div>
      <div class="twic-item md">
        <TwicImg src={imgUrl} />
        <span
          >class
          <Code>md</Code>
        </span>
      </div>
      <div class="twic-item sm">
        <TwicImg src={imgUrl} />
        <span
          >class
          <Code>sm</Code>
        </span>
      </div>
    </div>
  </TwicWrapper>
</div>

<style lang="scss">
  #twic-style-driven-container {
    h2 {
      margin-bottom: 30px;
    }

    .twic-grid {
      margin-bottom: 60px;
    }

    :global(.twic-item .twic-w) {
      background-color: #00ffa3;
      display: block;
    }

    .landscape {
      --twic-ratio: calc(4 / 3);
    }
    .portrait {
      --twic-ratio: calc(3 / 4);
    }
    .square {
      --twic-ratio: calc(1);
    }

    .contain {
      --twic-mode: contain;
    }

    .cover {
      --twic-mode: cover;
    }

    .left {
      --twic-position: left;
    }

    .right {
      --twic-position: right;
    }

    .lg {
      width: 300px;
    }

    .md {
      width: 150px;
    }

    .sm {
      width: 100px;
    }
  }
</style>
