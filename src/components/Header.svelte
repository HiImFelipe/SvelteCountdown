<script lang="ts">
  export let title: string;
  export let description: string;
</script>

<div>
  <h1>{title}</h1>
  <p>{description}</p>
</div>

<style>
  h1 {
    color: var(--primary);
    text-transform: uppercase;
    font-size: var(--font-xlarge);
    font-weight: 100;
  }

  p {
    color: var(--neutral);
    font-size: var(--font-xxsmall);
  }

  @media (min-width: 768px) {
    h1 {
      font-size: var(--font-xxxlarge);
    }

    p {
      font-size: var(--font-small);
    }
  }
</style>
