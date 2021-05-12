<script>
  export let key, isParentExpanded, isParentArray = false, colon = ':';

  $: showKey = (isParentExpanded || !isParentArray || key != +key);
</script>
<style>
  label {
    display: inline-block;
    color: var(--label-color);
    padding: 0;
  }
  .spaced {
    padding-right: var(--li-colon-space);
  }
</style>
{#if showKey && key}
  <label for="key" class:spaced={isParentExpanded} on:click>
    <span name="key">{key}{colon}</span>
  </label>
{/if}