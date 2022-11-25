<script>
  import TwicAbstract from './components/demo-wrapper/TwicAbstract.svelte';
  import TwicWrapper from './components/demo-wrapper/TwicWrapper.svelte';
  import { TwicImg } from '@twicpics/components/svelte3';

  let imageIndex = 0;
  let state;

  const onPreviousImage = () => {
    if (imageIndex === 0) {
      imageIndex = images.length;
    }
    imageIndex--;
  };

  const onNextImage = () => {
    imageIndex = (imageIndex + 1) % images.length;
  };

  const handleStateChange = (e) => {
    console.log(`Svelte - TwicImg emits new state`, e.detail);
  };

  $: {
    console.log(state);
  }

  $: imageReady = state === `error` || state === `loaded`;

  const images = [
    {
      url: `components/slideshow/space-1.jpg`,
      focus: ``
    },
    {
      url: `components/slideshow/space-2.jpg`,
      focus: `50px100p`
    },
    {
      url: `components/slideshow/space-3.jpg`,
      focus: `50px100p`
    },
    {
      url: `components/slideshow/space-4.jpg`,
      focus: `50px100p`
    },
    {
      url: `components/slideshow/space-5.jpg`,
      focus: `50px100p`
    },
    {
      url: `error.jpg`,
      focus: `50px100p`
    }
  ];
</script>

<!-- demonstrates mode features (contain or cover) -->
<TwicWrapper>
  <div class="container">
    <TwicAbstract title="Lifecycle" />
    <div>
      <label>Image status is: {state}</label>
    </div>
    <button class="slick-prev slick-arrow" on:click={onPreviousImage} disabled={!imageReady}>
      &#8249;
    </button>
    <div className="twic-item">
      <TwicImg
        on:statechange={handleStateChange}
        bind:state
        src={images[imageIndex].url}
        focus={images[imageIndex].focus}
        ratio="21/9"
      />
    </div>
    <button class="slick-next slick-arrow" on:click={onNextImage} disabled={!imageReady}>
      &#8250;
    </button>
  </div>
</TwicWrapper>

<style lang="scss">
  .container {
    position: relative;

    .twic-item {
      padding-bottom: 8px !important;
      margin-bottom: 8px;
    }
  }

  .slick-arrow {
    border: 0;
    border-radius: 50%;
    color: #000;
    cursor: pointer;
    display: block;
    font-size: 2rem;
    position: absolute;
    height: 3rem;
    width: 3rem;
    top: 60%;
    outline: 0;
    opacity: 0.5;
    padding-bottom: 5px;
    &:hover {
      opacity: 0.75;
    }

    &.slick-prev {
      left: -4rem;
    }

    &.slick-next {
      right: -4rem;
    }
    &:disabled {
      cursor: not-allowed;
      opacity: 0.2;
    }
  }
</style>
