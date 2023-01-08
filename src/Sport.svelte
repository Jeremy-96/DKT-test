<script>
  export let id;

  let sport;
  const promise = fetchItem();

  async function fetchItem(){
    const res = await fetch(`https://sports.api.decathlon.com/sports/${id}`);    
    const json = await res.json();

    sport = json.data;

    return sport;
  }
</script>

<!-- HTML start -->
<div class="container">
  {#await promise}
    <p>Chargement...</p>
  {:then sport}
    <div class="card">
      <div class="card-header">
        <img src="{sport.attributes.icon}" alt="{sport.name}">
        <h2>{sport.attributes.name}</h2>
        <button class="close-btn" onclick="history.back()">
          <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M6.99999 5.58599L11.95 0.635986L13.364 2.04999L8.41399 6.99999L13.364 11.95L11.95 13.364L6.99999 8.41399L2.04999 13.364L0.635986 11.95L5.58599 6.99999L0.635986 2.04999L2.04999 0.635986L6.99999 5.58599Z" fill="#00689D"/>
          </svg>  
        </button>
      </div>
      {#if sport.attributes.description}
        <p class="card-description">{sport.attributes.description}</p>
      {/if}
      {#if sport.relationships.tags.data}
        <div class="card-tags">
          {#each sport.relationships.tags.data as tag}
            <span class="tag">{tag}</span>
          {/each}
        </div>
      {/if}
    </div>
  {:catch error}
    <p>Une erreur est survenue : {error}</p>
  {/await}
</div>
<!-- HTML end -->


<style>
.container {
  z-index: 10;
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  padding: 1.25rem;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba(0, 16, 24, 0.8);
}
.card {
  z-index: 15;
  width: 600px;
  min-height: 300px;
  padding:  1rem 2rem;
  display: flex;
  flex-direction: column;
  align-items:flex-start;
  justify-content: space-around;
  background: #FFFFFF;
  box-shadow: 0px 24px 24px rgba(0, 83, 125, 0.1);
  border-radius: 8px;
  opacity: 100%;
}
.card-header {
  position: relative;
  width: 100%;
  height: 20%;
  display: flex;
  align-items: center;
  justify-content: flex-start;
}
img {
  width: 3.5rem;
  object-fit: cover;
}
h2 {
  text-align: center;
  margin: 0 0 0 1rem;
}
.close-btn {
  position:absolute;
  right: 0;

  background-color: #FFFFFF;
}
.card-description {
  width: 100%;
  height: 50%;
  margin: 2rem 0;
}
.card-tags {
  width: 100%;
  height: 30%;
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
}
.tag {
  width: auto;
  padding: 2px 8px;
  margin: 0.2rem;
  line-height: 1rem;
  font-size: 12px;
  color: #001018;
  background: #EFF1F3;
  border-radius: 4px;
}

/* Breakpoints for tablet & mobile start */
@media screen and (max-width: 768px){
  .card {
    padding: 1rem 1.5rem;
  }
}
/* Breakpoints for tablet & mobile end */
</style>