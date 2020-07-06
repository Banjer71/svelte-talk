<script>
  let logo = "../../Svelte_Logo.svg";
</script>

<style>
  nav {
    margin: 30px;
  }

  .navbar {
    display: flex;
    align-items: center;
    list-style-type: none;
  }

  .navbar li a {
    padding: 10px;
    color: white;
    text-decoration: none;
  }

  .navbar li:first-child {
    margin-right: auto;
  }

  nav img {
    width: 50px;
    margin: 10px;
  }

  @media only screen and (min-width: 780px) {
    nav {
      grid-row: 1;
      grid-column: 2/3;
      margin: 0;
    }

    nav img {
      width: 100px;
      margin: 10px;
    }

    .navbar {
      margin-right: 100px;
    }
  }
</style>

<nav>
  <ul class="navbar">
    <li>
      <a href="#logo">
        <img src={logo} alt={`${logo} logo`} />
      </a>
    </li>
    <li>
      <a href="#twitter">
        <i class="fab fa-twitter" />
      </a>
    </li>
    <li>
      <a href="#facebook">
        <i class="fab fa-facebook" />
      </a>
    </li>
    <li>
      <a href="#mail">
        <i class="far fa-envelope" />
      </a>
    </li>
  </ul>
</nav>
