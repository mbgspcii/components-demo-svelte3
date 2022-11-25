<script>
  const LOGOS_PATH = `https://assets.twicpics.com/demo/@twicpics-components/logos/`;
  const logoClass = `svelte-logo`;
  const logoSrc = `${LOGOS_PATH}svelte.png`;
  const logoAlt = `Svelte logo`;
  const redirect = `https://www.twicpics.com/docs/components/svelte-3`;
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
  #twic-header {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 30px;
    border-bottom: 1px solid #e3e3e4;
    background-color: #f9fafb;
    & a {
      text-decoration: none;
      color: initial;
    }
    & .heading-primary {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 10px;
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
    }

    & .tag {
      display: flex;
      align-items: center;
      gap: 4px;
      padding: 8px 16px;
      font-weight: 600;
      border-radius: 30px;
      box-shadow: 0 4px 4px rgba(0, 0, 0, 0.1);
      background-color: #06ffa3;
    }

    & .tag--bg-purple-rain {
      color: #fff;
      background-color: #8f00ff;
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
        background: linear-gradient(to right, #06ffa3, #8f00ff);
      }
      &:after {
        content: url('../../../assets/arrow-icon.svg');
        width: 20px;
        height: 20px;
      }
    }
  }

  @media screen and (min-width: 768px) {
    #twic-header .heading-primary {
      margin-bottom: 0;
    }

    #twic-header .tags-container {
      position: absolute;
      bottom: 0;
      left: 50%;
      transform: translate(-50%, 50%);
    }
  }
</style>
