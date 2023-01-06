<script>

</script>

<!-- HTML start -->
<header>
  <nav>
    <a href="#">Accueil</a>
    <a href="#">All sports</a>
  </nav>

  <div class="header-title">
    <h1 class="title">LOOKING FOR A NEW SPORT ?</h1>
    <p class="subtitle">Discover more than 500 sports and find your challenge.</p>
  </div>

  <div class="header-search">
    <div class="searchbar"></div>
  </div>
</header>
<!-- HTML end -->

<style>
  header {
    width: 100%;
    height: 492px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    background: linear-gradient(213.86deg, #007DBC 9.8%, #016AAF 46%, #0154A0 86.5%);
  }
  nav {
    width: 100%;
    height: 32px;
    padding: 0 0 0 80px;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    background-color: #FFFFFF;
    opacity: 65%;
  }
  a {
    color: #4E5D6B;
    margin: 0 1rem 0 0;
  }
  .header-title {
    width: 100%;
    padding: 0 0 0 80px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
    color: #FFFFFF; 
  }
  .title {
    margin: 0 0 24px 0;
    font-family: "Roboto Condensed", sans-serif;
    font-style: italic;
    font-weight: 700;
    font-size: 46px;
    line-height: 46px;
  }
  .subtitle {
    font-weight: 400;
    font-size: 18px;
    line-height: 28px;
  }
  .header-search {
    width: 100%;
    height: 122px;
    padding: 0 250px;
    display: flex;
    justify-content: center;
  }
  .searchbar {
    width: 100%;
    height: 82px;
    background-color: #FFFFFF;
    border-radius: 6px;
  }
</style>