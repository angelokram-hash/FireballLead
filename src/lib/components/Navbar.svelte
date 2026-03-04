<script lang="ts">
  let { dark = false } = $props();
  let menuOpen = $state(false);
</script>

<nav style="
  position:fixed; top:0; left:0; right:0; z-index:100;
  padding:1rem 2rem;
  background:{dark ? 'rgba(26,60,64,0.95)' : 'rgba(255,255,255,0.95)'};
  backdrop-filter:blur(12px);
  border-bottom:1px solid {dark ? 'rgba(255,255,255,0.08)' : 'rgba(0,0,0,0.06)'};
">
  <div style="max-width:1200px; margin:0 auto; display:flex; align-items:center; justify-content:space-between;">
    <a href="/" class="fireball-brand" style="
      font-size:1.25rem;
      color:{dark ? '#C8A951' : 'var(--teal)'};
      text-decoration:none;
    ">FIREBALL</a>

    <a href="/#kontakt" class="btn-primary" style="
      padding:0.5rem 1.25rem;
      font-size:0.85rem;
    ">Partner werden</a>
  </div>
</nav>
