<script>
  const LOGOS_PATH = `https://assets.twicpics.com/demo/@twicpics-components/logos/`;
  const logoClass = `svelte-logo`;
  const logoSrc = `${LOGOS_PATH}svelte.png`;
  const logoAlt = `Svelte logo`;
  const redirect = `https://www.twicpics.com/docs/components/svelte-3`;
  export let gitHubUrl = `https://github.com/TwicPics/components-demo-svelte3`;
</script>

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
    <a target="_blank" href={gitHubUrl} rel="noreferrer">GitHub</a>
  </div>
  <div class="tags-container">
    <div class="tag">@twicpics-components</div>
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

<style lang="scss">
  $bg-color: #f9fafb;
  $deep-purple: #8f00ff;
  $green: #06ffa3;
  #twic-header {
    height: 100px;
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 30px;
    border-bottom: 1px solid #e3e3e4;
    background-color: $bg-color;
    & a {
      text-decoration: none;
      color: initial;

      &#go-to-github {
        position: absolute;
        right: 0px;
        top: 0px;
        bottom: 0px;

        & div {
          border-top: 100px solid darken($bg-color, 5%);
          border-left: 100px solid transparent;

          & img {
            position: absolute;
            top: 10px;
            right: 10px;
            transform: rotate(45deg);
          }
        }
      }
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
      font-size: 0.9em;
      position: absolute;
      bottom: 0;
      left: 50%;
      transform: translate(-50%, 50%);
    }

    & .tag {
      display: flex;
      align-items: center;
      gap: 4px;
      padding: 8px 16px;
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
      background-color: $deep-purple;
      overflow: hidden;
      white-space: nowrap;
      position: absolute;
      right: -38px;
      top: 16px;
      -webkit-transform: rotate(45deg);
      -moz-transform: rotate(45deg);
      -ms-transform: rotate(45deg);
      -o-transform: rotate(45deg);
      transform: rotate(45deg);
      -webkit-box-shadow: 0 0 10px #888;
      -moz-box-shadow: 0 0 10px #888;
      box-shadow: 0 0 10px #888;
    }
    .ribbon a {
      border: 1px solid darken($deep-purple, 25);
      color: #fff;
      display: block;
      font: bold 81.25% 'Helvetica Neue', Helvetica, Arial, sans-serif;
      margin: 1px 0;
      padding: 10px 50px;
      text-align: center;
      text-decoration: none;
      text-shadow: 0 0 5px #444;
    }
  }
</style>
