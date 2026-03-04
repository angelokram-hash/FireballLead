<script lang="ts">
  let { channel = '', ctaText = 'Jetzt anfragen', brancheOptions = [] as string[] } = $props();

  let name = $state('');
  let company = $state('');
  let email = $state('');
  let phone = $state('');
  let branche = $state('');
  let standorte = $state('');
  let submitted = $state(false);
  let isValid = $derived(name.length > 0 && company.length > 0 && email.includes('@'));

  function handleSubmit() {
    if (!isValid) return;
    // In production: send to CRM API
    console.log('Lead submitted:', { name, company, email, phone, branche, standorte, channel });
    submitted = true;
  }
</script>

{#if submitted}
  <div class="animate-fade-up" style="text-align:center; padding:3rem 2rem;">
    <div style="font-size:3rem; margin-bottom:1rem;">✓</div>
    <h3 style="font-family:'Josefin Sans',sans-serif; color:var(--teal); font-size:1.5rem; margin-bottom:0.5rem;">
      Vielen Dank!
    </h3>
    <p style="color:var(--gray-500);">
      Wir melden uns innerhalb von 24 Stunden bei Ihnen.
    </p>
  </div>
{:else}
  <div style="display:flex; flex-direction:column; gap:1rem;">
    <div style="display:grid; grid-template-columns:1fr 1fr; gap:1rem;">
      <input class="form-input" bind:value={name} placeholder="Ihr Name *" required />
      <input class="form-input" bind:value={company} placeholder="Geschäftsname *" required />
    </div>
    <div style="display:grid; grid-template-columns:1fr 1fr; gap:1rem;">
      <input class="form-input" type="email" bind:value={email} placeholder="E-Mail *" required />
      <input class="form-input" type="tel" bind:value={phone} placeholder="Telefon" />
    </div>
    {#if brancheOptions.length > 0}
      <select class="form-input" bind:value={branche}>
        <option value="">Branche wählen...</option>
        {#each brancheOptions as opt}
          <option value={opt}>{opt}</option>
        {/each}
      </select>
    {/if}
    <input class="form-input" bind:value={standorte} placeholder="Anzahl Standorte (optional)" />
    <button
      class="btn-primary"
      style="width:100%; justify-content:center; margin-top:0.5rem; opacity:{isValid ? 1 : 0.5};"
      onclick={handleSubmit}
      disabled={!isValid}
    >
      {ctaText} →
    </button>
    <p style="font-size:0.75rem; color:var(--gray-500); text-align:center; margin:0;">
      Ihre Daten werden vertraulich behandelt. Kein Spam.
    </p>
  </div>
{/if}

<style>
  @media (max-width: 640px) {
    div[style*="grid-template-columns:1fr 1fr"] {
      grid-template-columns: 1fr !important;
    }
  }
</style>
