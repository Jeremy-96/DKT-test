<script context="module">
// Store the input value of the searchbar
let searchQuery = "";
// Set the checkbox value to false
let hasDktId = false;

/**
 * Listen input value in the searchbar
 * @function handleSearch
 * @param event
 * @author Jérémy Thonon <jeremythonon96@hotmail.com>
 */
function handleSearch(event){
  searchQuery = event.target.value;
}

/**
 * Submit all input values of the searchbar form and store them in the localStorage
 * @function handleSubmit
 * @param event
 * @author Jérémy Thonon <jeremythonon96@hotmail.com>
 */
function handleSubmit(event){
  event.preventDefault();
  localStorage.setItem('input', searchQuery);
  localStorage.setItem('hasDktID', hasDktId);
  window.location.reload();
}
</script>

<!-- HTML start -->
<header>
  <nav>
    <a href="/">Accueil</a>
    <a class="one" href="/">All sports</a>
  </nav>

  <div class="header-title">
    <h1 class="title">LOOKING FOR A NEW SPORT ?</h1>
    <p class="subtitle">Discover more than 500 sports and find your challenge.</p>
  </div>

  <div class="header-search">
    <form class="searchbar" on:submit|preventDefault={handleSubmit}>
      <div class="sport-input">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M16.024 15.0588H17.1123L23.9435 21.9037L21.9037 23.9435L15.0588 17.1123V16.0308L14.6824 15.6544C13.1286 16.9891 11.1093 17.7968 8.89842 17.7968C3.98374 17.7968 0 13.8131 0 8.89842C0 3.98374 3.98381 0 8.89842 0C13.813 0 17.7968 3.98374 17.7968 8.89842C17.7968 11.1093 16.9891 13.1286 15.6475 14.6824L16.024 15.0588ZM2.73799 8.89842C2.73799 12.3003 5.49651 15.0588 8.89842 15.0588C12.3003 15.0588 15.0588 12.3003 15.0588 8.89842C15.0588 5.49651 12.3003 2.73799 8.89842 2.73799C5.49651 2.73799 2.73799 5.49651 2.73799 8.89842Z" fill="#007DBC"/>
        </svg>
          
        <label for="text">Text</label>
        <input id="text" type="search"  bind:value={searchQuery} on:input={handleSearch} placeholder="Search by name">
      </div>

      <div class="id-input">
        <input id="checkbox" bind:checked={hasDktId} type="checkbox">
        <label for="checkbox" disabled>Only sports represented at Decathlon</label>
      </div>
  
      <button class="submit-btn" type="submit" >Search</button>
    </form>
  </div>
</header>
<!-- HTML end -->

<style>
header {
  width: 100%;
  min-height: 492px;
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
.one {
  color:#001018;
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
  position: relative;
  width: 100%;
  height: 82px;
  padding: 0 1rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #FFFFFF;
  border-radius: 6px;
}
.sport-input, .id-input, .submit-btn  {
  display: flex;
  align-items: center;
}
.sport-input, .id-input {
  height: 100%;
}
.sport-input {
  width: 50%;
  border-right: 1px solid #6E8098;
}
.sport-input svg {
  margin: 0 1rem;
}
.sport-input label {
  display: none;
}
.sport-input input {
  width: 80%;
}
.id-input {
  justify-content: space-center;
  line-height: 19px;
}
.id-input input {
  width: 24px;
  height: 24px;
  margin: 0 1rem;
  border-radius: 3px;
  border: none;
  background-color:#19202D;
}
.id-input input::placeholder {
  width: auto;
  color:#19202D;
}
.id-input label {
  font-weight: 700;
}
.submit-btn {
  width: 10%;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  color:#FFFFFF;
  border-radius: 5px;
}

/* Breakpoints for tablet & mobile start */
@media screen and (max-width: 1024px){
  .header-search, .header-title {
    padding: 0 2rem;
  }
}

@media screen and (max-width: 768px) {
  .title {
    margin: 0;
  }
  .header-search {
    height: 250px;
  }
  .searchbar{
    height:150px;
    padding:0;
    flex-direction: column;
  }
  .sport-input{
    width: 100%;
    border-right: 0;
    border-bottom: 1px solid #6E8098;
    align-items: center;
    justify-content: center;
  }
  .submit-btn{
    position: absolute;
    bottom: -4rem;
    width: 10rem;
  }
}
/* Breakpoints for tablet & mobile end */
</style>