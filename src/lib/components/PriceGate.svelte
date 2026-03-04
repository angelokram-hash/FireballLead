<script lang="ts">
  let { unlocked = $bindable(false) } = $props();
  let pw = $state('');
  let error = $state(false);

  function unlock() {
    if (pw === 'xxopen' || pw === 'open') {
      unlocked = true;
      error = false;
    } else {
      error = true;
      pw = '';
    }
  }
</script>

<!-- svelte-ignore a11y_click_events_have_key_events -->
<!-- svelte-ignore a11y_no_static_element_interactions -->
<div style="position:fixed; inset:0; background:rgba(0,0,0,0.6); z-index:1000; display:flex; align-items:center; justify-content:center; padding:2rem;">
  <div onclick={(e) => e.stopPropagation()} style="background:var(--teal); padding:2.5rem; max-width:380px; width:100%; border:1px solid rgba(255,255,255,0.1);">
    <p class="fireball-brand" style="color:var(--gold); font-size:1.2rem; margin-bottom:0.25rem; text-align:center;">FIREBALL</p>
    <p style="color:rgba(255,255,255,0.5); font-size:0.8rem; text-align:center; margin-bottom:1.5rem;">Partner-Preise & Konditionen freischalten</p>
    <input
      type="password"
      bind:value={pw}
      onkeydown={(e) => { if (e.key === 'Enter') unlock(); }}
      placeholder="Partner-Passwort"
      style="
        width:100%; padding:0.75rem 1rem; border:1px solid {error ? '#e74c3c' : 'rgba(255,255,255,0.15)'};
        background:rgba(255,255,255,0.05); color:white; font-size:1rem;
        font-family:'DM Sans',sans-serif; outline:none; box-sizing:border-box;
        margin-bottom:0.5rem;
      "
    />
    {#if error}<p style="color:#e74c3c; font-size:0.75rem; margin:0 0 0.5rem;">Falsches Passwort.</p>{/if}
    <button onclick={unlock} style="
      width:100%; padding:0.75rem; background:var(--gold); color:var(--teal);
      border:none; cursor:pointer; font-family:'Josefin Sans',sans-serif;
      font-size:0.9rem; letter-spacing:0.1em; font-weight:600; margin-top:0.25rem;
    ">Freischalten</button>
    <p style="color:rgba(255,255,255,0.25); font-size:0.65rem; text-align:center; margin-top:0.75rem;">Passwort erhalten Sie von Ihrem FIREBALL Ansprechpartner.</p>
  </div>
</div>
