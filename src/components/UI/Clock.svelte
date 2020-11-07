<script>
  import { onMount } from "svelte";

  let date = new Date();
  const options = {
    hour: "2-digit",
    minute: "2-digit",
    second: "2-digit",  };
  const formatter = new Intl.DateTimeFormat("fr", options);
//   $: console.log(dateFormat);

  // these automatically update when `time`
  // changes, because of the `$:` prefix
  //   let hours = time.getHours();
  //   let minutes = time.getMinutes();
  //   let seconds = time.getSeconds();

  onMount(() => {
    const interval = setInterval(() => {
      date = new Date();
    }, 1000);
    // console.log(hours);
    //  if (hours.length < 2) hours = "0" + hours;
    //  if (minutes.length < 2) minutes = "0" + minutes;
    //  if (seconds.length < 2) seconds = "0" + seconds;

    return () => {
      clearInterval(interval);
    };
  });
</script>

<div>{formatter.format(date)}</div>
