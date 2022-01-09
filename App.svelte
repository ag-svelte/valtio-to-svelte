<script>
  import data, { toSvelteStore } from "./data";

  const snapshotStore = toSvelteStore(data);
  const countSnapshotStore = toSvelteStore(data.count);

  $: console.log("snapshotStore changed!", $snapshotStore);
  $: console.log("countSnapshotStore changed!", $countSnapshotStore);
</script>

<button on:click={() => data.count.value--}>-</button>
{$snapshotStore.count.value}
<button on:click={() => data.count.value++}>+</button>

<input bind:value={data.text} />
{$snapshotStore.text}