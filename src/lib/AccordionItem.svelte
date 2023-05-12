<script lang="ts">
  export let title: string;
  export let subtitle: string = "";
  export let opened: boolean = false;
  let icon = '';
  $: opened, icon = opened ? '-' : '+';

  function onClick(){
    opened = !opened;
  }
</script>

<li class="ml-2 sm:ml-5">
  <div>
  <button class="hover:bg-primary hover:text-primary-content text-lg sm:text-xl" on:click={onClick}>
    [{icon}] {title}
  </button>
  {#if subtitle != ""}
  <span class="opacity-50 overflow-hidden whitespace-nowrap">
    // {subtitle}
  </span>
  {/if}
  </div>
  <div class={`${opened ? 'mb-8 mt-2' : 'hidden'} text-base`}>
  <slot/>
  </div>
</li>
