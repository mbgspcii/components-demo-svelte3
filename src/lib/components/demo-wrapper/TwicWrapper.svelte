<script>
  import githubLogo from '../../../assets/github-mark-white.svg';
  import stackBlitzLogo from '../../../assets/stackblitz.svg';

  export let gitHubUrl = undefined;

  const LOGOS_PATH = `https://assets.twicpics.com/demo/@twicpics-components/logos/`;
  const logoClass = `svelte-logo`;
  const logoSrc = `${LOGOS_PATH}svelte.png`;
  const logoAlt = `Svelte logo`;
  const redirect = `https://www.twicpics.com/docs/components/svelte-3?utm_source=github&utm_medium=organic&utm_campaign=components`;
  const GITHUB = `https://github.com/TwicPics/components-demo-svelte3/blob/main`;
  const CODESANDBOX = `https://stackblitz.com/edit/github-wpprt7?file=`;

  $: _codeSandBoxUrl = `${CODESANDBOX}${gitHubUrl || 'README.md'}`;
  $: _gitHubUrl = gitHubUrl ? `${GITHUB}/blob/main/${gitHubUrl}` : GITHUB;
</script>

<div id="twic-demo-wrapper" class="">
  <header id="twic-header">
    <a href="/" title="Home">
      <h1 class="heading-primary">
        <img
          class="twicpics-logo"
          src="https://assets.twicpics.com/demo/@twicpics-components/logos/twicpics.svg"
          alt="TwicPics logo"
        />
        <span>x</span>
        <img class={logoClass} src={logoSrc} alt={logoAlt} />
      </h1>
    </a>
    <div class="ribbon">
      <div>
        <a target="_blank" href={_gitHubUrl} rel="noreferrer" title="Open in Github"
          ><img class="github" src={githubLogo} alt="Open in Github" /></a
        >
        <a target="_blank" href={_codeSandBoxUrl} rel="noreferrer" title="Open in StackBlitz"
          ><img class="github" src={stackBlitzLogo} alt="Open in StackBlitz" /></a
        >
      </div>
    </div>
    <div class="tags-container">
      <div class="tag tag-components">@twicpics-components</div>
      <a
        href={redirect}
        target="_blank"
        class="documentation-link tag tag--bg-purple-rain"
        rel="noreferrer"
      >
        Documentation
      </a>
    </div>
  </header>
  <main id="twic-demo-container">
    <slot />
  </main>
</div>

<style lang="scss">
  $bg-color: #f9fafb;
  $bg-github: #6d6d6d;
  $deep-purple: #8f00ff;
  $ribbon-height: 30px;
  $green: #06ffa3;
  $height: 100px;

  #twic-demo-wrapper {
    & #twic-demo-container {
      margin-top: $height + 40px;
      max-width: 1500px;
    }
  }

  #twic-demo-wrapper {
    & #twic-demo-container {
      @media screen and (min-width: 768px) {
        margin: 80px 60px;
        margin-top: $height + 80px;
      }
      @media screen and (min-width: 1600px) {
        margin: 2rem auto;
        margin-top: calc($height + 2rem);
      }
    }
  }

  #twic-header {
    height: $height;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 30px;
    border-bottom: 1px solid #e3e3e4;
    background-color: $bg-color;
    z-index: 10;
    & a {
      text-decoration: none;
      color: initial;
    }
    & .heading-primary {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 0px;
      font-size: 1.2em;
      font-weight: 400;
    }
    & .twicpics-logo {
      aspect-ratio: 140/39;
      width: 140px;
    }
    & .svelte-logo {
      aspect-ratio: 7/3;
      width: 100px;
    }
    & .tags-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 12px;
      width: 100%;
      position: absolute;
      bottom: 0;
      left: 50%;
      transform: translate(-50%, 50%);
    }
    & .tag {
      display: flex;
      align-items: center;
      gap: 4px;
      font-weight: 600;
      border-radius: 30px;
      box-shadow: 0 4px 4px rgba(0, 0, 0, 0.1);
      background-color: $green;
    }
    & .tag--bg-purple-rain {
      color: #fff;
      background-color: $deep-purple;
    }
    & .documentation-link {
      &:link,
      &:visited {
        text-decoration: none;
        transition: all 0.3s;
      }
      &:hover,
      &:active {
        transform: translateY(-5px);
        box-shadow: 0 9px 4px rgba(0, 0, 0, 0.09);
        background: linear-gradient(to right, $green, $deep-purple);
      }
      &:after {
        content: url('../../../assets/arrow-icon.svg');
        width: 20px;
        height: 20px;
      }
    }
    .ribbon {
      background-color: $bg-github;
      overflow: hidden;
      white-space: nowrap;
      position: absolute;
      left: -33px;
      top: 20px;
      transform: rotate(-45deg);
      box-shadow: 0 0 5px #888;
      & div {
        color: #fff;
        display: block;
        font: bold 81.25% 'Helvetica Neue', Helvetica, Arial, sans-serif;
        width: 1.42 * $height;
        line-height: $ribbon-height;
        text-align: center;
        & a {
          margin-right: 5px;
          & img {
            height: 23px;
            width: 23px;
            line-height: 23px;
            vertical-align: middle;
            margin-top: -4px;
            transition-duration: 200ms;
            &:hover {
              transform: rotate(45deg);
            }
          }
        }
      }
    }
    .tags-container {
      font-size: 0.7em;
      @media (min-width: 640px) {
        font-size: 0.9em;
      }
    }
    .tag {
      padding: 4px 8px;
      @media (min-width: 640px) {
        padding: 8px 16px;
      }
    }
    .github {
      width: 20px;
      & svg path {
        fill: blue;
      }
    }
  }
</style>
