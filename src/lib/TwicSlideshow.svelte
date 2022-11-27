<script>
  import TwicAbstract from './components/demo-wrapper/TwicAbstract.svelte';
  import TwicWrapper from './components/demo-wrapper/TwicWrapper.svelte';
  import Slideshow from './components/Slideshow.svelte';

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
    }
  ];
</script>

<!-- displays a carousel of responsive images -->
<TwicWrapper
  gitHubUrl="https://github.com/TwicPics/components-demo-svelte3/blob/main/src/lib/TwicSlideshow.svelte"
>
  <div class="twic-slideshow-container">
    <TwicAbstract
      title="A Picture Carousel"
      codeSandBoxUrl="https://codesandbox.io/p/github/TwicPics/components-demo-svelte3/main?file=%2Fsrc%2Flib%2FTwicSlideshow.svelte&hidenavigation=1"
      codeSandBoxName="TwicPics x Svelte - Picture Carousel"
    >
      <p>
        Use TwicPics for automatic lazy-loading, CLS optimization and art directions adaptation.
      </p>
      <p>
        <strong>Change the width of your browser</strong> to see the image aspect-ratio adapt according
        to the CSS rules.
      </p>
    </TwicAbstract>
    <Slideshow {images} />
  </div>
</TwicWrapper>

<style lang="scss">
  .twic-slideshow-container {
    margin: auto;
    width: 75%;
  }
</style>
