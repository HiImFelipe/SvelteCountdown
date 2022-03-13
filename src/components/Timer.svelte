<script lang="ts">
  export const convertMilisecondsToMinutes = (value: number) => {
    return Math.floor(value / 60 / 1000);
  };

  export const convertMilisecondsToSeconds = (value: number) => {
    return Math.floor(value / 1000) % 60;
  };

  const timerStartValue = 5 * 60 * 1000; // 5 minutes in miliseconds;

  let timer = timerStartValue;
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

  const resetDefaultValues = () => {
    timer = timerStartValue;
    minutes = convertMilisecondsToMinutes(timer);
    seconds = convertMilisecondsToSeconds(timer);

    minutesWithPadStart = minutes.toString().padStart(2, "0");
    secondsWithPadStart = seconds.toString().padStart(2, "0");
  };

  startTimer();
</script>

<section>
  <div class="timerContainer">
    <p class="timerText">{minutesWithPadStart} : {secondsWithPadStart}</p>

    <div>
      {#if timer <= 0}
        <p class="timerEndReached">You've reached the timer's end</p>

        <button on:click={resetDefaultValues}> Start Over </button>
      {/if}
    </div>
  </div>
</section>

<style>
  section {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }
  div.timerContainer {
    display: flex;
    justify-content: center;
    flex-direction: column;
    width: 100%;
  }

  p.timerText {
    font-size: var(--font-large);
    color: var(--neutral);
    margin: 0;
  }

  p.timerEndReached {
    font-size: var(--font-xxsmall);
    color: var(--neutral);
  }

  button {
    font-size: var(--font-xxsmall);
    color: var(--neutral);
    background-color: var(--secondary);
    border: none;
    padding: 1em 2em;
    border-radius: 5px;
    cursor: pointer;
  }

  @media (min-width: 768px) {
    p.timerText {
      font-size: var(--font-xxlarge);
    }

    p.timerEndReached {
      font-size: var(--font-xsmall);
    }

    button {
      font-size: var(--font-xsmall)
    }
  }
</style>
