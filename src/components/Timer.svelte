<script lang="ts">
  export const convertMilisecondsToMinutes = (value: number) => {
    return Math.floor(value / 60 / 1000);
  };

  export const convertMilisecondsToSeconds = (value: number) => {
    return Math.floor(value / 1000) % 60;
  };

  let timer = 5 * 60 * 1000; // 5 minutes in miliseconds;
  let minutes = convertMilisecondsToMinutes(timer);
  let seconds = convertMilisecondsToSeconds(timer);

  let minutesWithPadStart = minutes.toString().padStart(2, "0");
  let secondsWithPadStart = seconds.toString().padStart(2, "0");

  const startTimer = () => {
    const interval = setInterval(() => {
      if (timer <= 0) {
        clearInterval(interval);
        return;
      }

      timer -= 1000;
      minutes = convertMilisecondsToMinutes(timer);
      seconds = convertMilisecondsToSeconds(timer);

      // Parse the minutes and seconds to string and add a leading zero if required.
      minutesWithPadStart = minutes.toString().padStart(2, "0");
      secondsWithPadStart = seconds.toString().padStart(2, "0");
    }, 1000);
  };

  startTimer();
</script>

<div>
  <p>{minutesWithPadStart} : {secondsWithPadStart}</p>
</div>

<style>
  div {
    display: flex;
    justify-content: center;
  }

  p {
    font-size: var(--font-large);
    color: var(--neutral);
  }

  @media (min-width: 768px) {
    p {
      font-size: var(--font-xxlarge);
    }
  }
</style>
