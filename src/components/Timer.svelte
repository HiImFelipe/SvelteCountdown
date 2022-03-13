<script lang="ts">
  export const convertMilisecondsToMinutes = (value: number) => {
    return Math.floor(value / 60 / 1000);
  };

  export const convertMilisecondsToSeconds = (value: number) => {
    return Math.floor(value / 1000) % 60;
  };

  let timer = 1000; // 5 minutes in miliseconds;
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

<section>
  <div>
    <p class="timer">{minutesWithPadStart} : {secondsWithPadStart}</p>

    <p class="timerEndReached">
      {timer === 0 ? "You've reached the timer's end" : ""}
    </p>
  </div>
</section>

<style>
  section {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }
  div {
    display: flex;
    justify-content: center;
    flex-direction: column;
    width: 100%;
  }

  p.timer {
    font-size: var(--font-large);
    color: var(--neutral);
  }

  p.timerEndReached {
    font-size: var(--font-xxsmall);
    color: var(--neutral);
  }

  @media (min-width: 768px) {
    p.timer {
      font-size: var(--font-xxlarge);
    }

    p.timerEndReached {
    font-size: var(--font-xsmall);
  }
  }
</style>
