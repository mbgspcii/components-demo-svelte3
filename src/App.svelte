<script>
  import router from 'page';
  import Home from './lib/Home.svelte';
  import Anchor from './lib/TwicAnchor.svelte';
  import ArtDirections from './lib/TwicArtDirections.svelte';
  import BasicGrid from './lib/TwicBasicGrid.svelte';
  import Bot from './lib/TwicBot.svelte';
  import FlipCards from './lib/TwicFlipCards.svelte';
  import Focus from './lib/TwicFocus.svelte';
  import GridAndZoom from './lib/TwicGridAndZoom.svelte';
  import Modal from './lib/TwicModal.svelte';
  import Mode from './lib/TwicMode.svelte';
  import Placeholder from './lib/TwicPlaceholder.svelte';
  import Position from './lib/TwicPosition.svelte';
  import PreTransform from './lib/TwicPreTransform.svelte';
  import Ratio from './lib/TwicRatio.svelte';
  import Slider from './lib/TwicSlider.svelte';
  import Slideshow from './lib/TwicSlideshow.svelte';
  import StyleDriven from './lib/TwicStyleDriven.svelte';
  import PageTemplating from './lib/TwicPageTemplating.svelte';
  import Transition from './lib/TwicTransition.svelte';
  import ShortVideos from './lib/TwicShortVideos.svelte';

  let page;

  router('/', () => (page = Home));
  router('/anchor', () => (page = Anchor));
  router('/art-directions', () => (page = ArtDirections));
  router('/basic-grid', () => (page = BasicGrid));
  router('/bot', () => (page = Bot));
  router('/flip-cards', () => (page = FlipCards));
  router('/focus', () => (page = Focus));
  router('/grid-and-zoom', () => (page = GridAndZoom));
  router('/modal', () => (page = Modal));
  router('/mode', () => (page = Mode));
  router('/placeholder', () => (page = Placeholder));
  router('/position', () => (page = Position));
  router('/pretransform', () => (page = PreTransform));
  router('/ratio', () => (page = Ratio));
  router('/slider', () => (page = Slider));
  router('/slideshow', () => (page = Slideshow));
  router('/style-driven', () => (page = StyleDriven));
  router('/transition', () => (page = Transition));
  router('/page-templating', () => (page = PageTemplating));
  router('/shortVideos', () => (page = ShortVideos));

  router.start();
</script>

<svelte:component this={page} />
