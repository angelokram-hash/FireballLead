<script lang="ts">
  import type { Snippet } from 'svelte';
  let { unlocked = false, onunlock = () => {}, children }: { unlocked: boolean, onunlock: () => void, children: Snippet } = $props();
</script>

<div class="pw" class:pw-locked={!unlocked}>
  <div class="pw-content" style="{!unlocked ? 'filter:blur(6px);user-select:none;pointer-events:none;' : ''}">
    {@render children()}
  </div>
  {#if !unlocked}
    <div class="pw-gate">
      <button onclick={onunlock} class="pw-btn">
        <span class="pw-icon">🔒</span>
        <span class="pw-label">Preise freischalten</span>
      </button>
    </div>
  {/if}
</div>

<style>
  .pw {
    position: relative;
  }
  .pw-locked {
    cursor: pointer;
  }
  .pw-content {
    transition: filter 0.4s ease;
  }
  .pw-gate {
    position: absolute;
    inset: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 10;
  }
  .pw-btn {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    padding: 0.85rem 1.75rem;
    background: var(--gold);
    color: var(--teal);
    border: none;
    cursor: pointer;
    font-family: 'Josefin Sans', sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
    letter-spacing: 0.05em;
    box-shadow: 0 4px 24px rgba(0,0,0,0.3);
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .pw-btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 32px rgba(0,0,0,0.4);
  }
  .pw-icon { font-size: 1rem; }
  .pw-label { font-size: 0.85rem; }
</style>
