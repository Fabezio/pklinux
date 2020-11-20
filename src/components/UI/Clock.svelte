<script>
  import { onMount } from "svelte";

  let date = new Date();
  const options = {
    hour: "numeric",
    minute: "2-digit",
    second: "2-digit",
  };
  const formatter = new Intl.DateTimeFormat("fr", options);

  onMount(() => {
    const interval = setInterval(() => {
      date = new Date();
    }, 1000);

    return () => {
      clearInterval(interval);
    };
  });
</script>

<div>{formatter.format(date)}</div>
