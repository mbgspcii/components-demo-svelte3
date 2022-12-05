<script>
  import TwicWrapper from './components/demo-wrapper/TwicWrapper.svelte';
  import { TwicImg, TwicVideo } from '@twicpics/components/svelte3';

  const categories = [
    {
      title: `Use cases`,
      items: [
        {
          route: `/art-directions`,
          imgSrc: `components/greece.jpg`,
          title: `Art directions`
        },
        {
          route: `/basic-grid`,
          imgSrc: `https://assets.twicpics.com/examples/football.jpg`,
          title: `Basic example`
        },
        {
          route: `/bulk-loading`,
          imgSrc: `https://assets.twicpics.com/examples/football.jpg`,
          title: `Bulk Loading`
        },
        {
          route: `/color-blindness`,
          imgSrc: `components/colored-balloons.jpg`,
          title: `Color Blindness`
        },
        {
          route: `/flip-cards`,
          imgSrc: `components/flip/orange-1.jpg`,
          title: `Flip cards`
        },
        {
          route: `/grid-and-zoom`,
          imgSrc: `components/portraits/woman-1.jpg`,
          title: `Grid & zoom`
        },
        {
          route: `/hero`,
          imgSrc: `components/goldenGate.jpg`,
          title: `Hero image`
        },
        {
          route: `/modal`,
          imgSrc: `components/modal/seagull.jpg`,
          title: `Modal`
        },
        {
          route: `/slider`,
          imgSrc: `components/slider/pantone.jpg`,
          title: `Slider`
        },
        {
          route: `/slideshow`,
          imgSrc: `components/slideshow/space-1.jpg`,
          title: `Slideshow`
        },
        {
          route: `/style-driven`,
          imgSrc: `components/horse.jpg`,
          title: `Style driven`
        },
        {
          route: `/page-templating`,
          imgSrc: `components/woman.jpg`,
          title: `Page templating`
        },
        {
          route: `/shortVideos`,
          videoSrc: `video/skater.mp4`,
          title: `Short videos`,
          intrinsic: '1280x720'
        }
      ]
    },
    {
      title: `Properties`,
      items: [
        {
          route: `/anchor`,
          imgSrc: `cat_1x1.jpg`,
          title: `anchor`
        },
        {
          route: `/bot`,
          imgSrc: `components/puppy.jpg`,
          title: `bot`
        },
        {
          route: `/focus`,
          imgSrc: `components/puppy.jpg`,
          title: `focus`
        },
        {
          route: `/intrinsic`,
          imgSrc: `components/fantasy.jpg`,
          title: `intrinsic`
        },
        {
          route: `/mode`,
          imgSrc: `components/fox.jpg`,
          title: `mode`
        },
        {
          route: `/placeholder`,
          imgSrc: `components/cat.jpg`,
          title: `placeholder`
        },
        {
          route: `/position`,
          imgSrc: `components/position/horse.jpg`,
          title: `position`
        },
        {
          route: `/pretransform`,
          imgSrc: `components/man-hiding-his-hands.jpg`,
          title: `preTransform`
        },
        {
          route: `/ratio`,
          imgSrc: `components/woman-and-winter.jpg`,
          title: `ratio`
        },
        {
          route: `/state`,
          imgSrc: `components/states/autumn.jpg`,
          title: `state`
        },
        {
          route: `/transition`,
          imgSrc: `components/peacock.jpg`,
          title: `transition`
        }
      ]
    }
  ];
</script>

<TwicWrapper>
  <div class="home-container">
    {#each categories as category}
      <div class="twic-panel">
        <h3>{category.title}</h3>
        <div class="twic-grid">
          {#each category.items as item}
            <a href={item.route}>
              <figure class="twic-item">
                {#if item.imgSrc}
                  <TwicImg src={item.imgSrc} focus="auto" ratio="0.95" />
                {:else}
                  <TwicVideo src={item.videoSrc} ratio="0.95" intrinsic={item.intrinsic} />
                {/if}
                <figcaption>
                  <p>{item.title}</p>
                </figcaption>
              </figure>
            </a>
          {/each}
        </div>
      </div>
    {/each}
  </div>
</TwicWrapper>

<style lang="scss">
  .home-container {
    h3 {
      margin-bottom: 1rem;
    }

    .twic-grid {
      --twic-grid-columns-width: calc(200px);
    }

    :global(.twic-item) {
      & :global(img) {
        transition: 0.3s all ease-in-out;
      }

      &:hover {
        & :global(img.twic-done) {
          transform: scale(1.1) !important;
        }
      }
    }

    figure {
      position: relative;
      & figcaption {
        position: absolute;
        right: 0;
        bottom: 0;
        left: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 12px;
        height: 40px;
        text-align: center;
        font-size: 1em;
        font-weight: 600;
        color: #fff;
        background: rgba(0, 0, 0, 0.5);
        transition: all 0.3s;
      }
      &:hover {
        cursor: pointer;
        & figcaption {
          bottom: 40%;
        }
      }
    }
  }
</style>
