<script>
  import { isActive, url } from "@sveltech/routify";
  const links = [
    ["./shop", "🛍️ Shop"],
    ["./stocks", "📈 Trade"],
    ["./fish", "🛰️ Go Fishing"],
    ["./ship", "🚀 Ship"],
    ["./log", "📝 Logs"],
    ["./settings", "⚙️ Settings"]
  ];
</script>

<style>
  .slotContainer {
    max-width: 800px;
    margin: 0 auto;
    padding: 10px;
    margin-top: 3rem;
  }
</style>

<nav>
  <div class="brand">
    <span>Space Fishing</span>
  </div>

  <!-- responsive-->
  <input id="bmenub" type="checkbox" class="show" />
  <label for="bmenub" class="burger pseudo button">menu</label>

  <div class="menu">
    {#each links as [path, name]}
      <a href={$url(path)} class="button" class:pseudo={!$isActive(path)}>
        {name}
      </a>
    {/each}
  </div>
</nav>

<div class="slotContainer">
  <slot />
</div>
