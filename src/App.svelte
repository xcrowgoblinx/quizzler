<script lang="ts">
  import BaselineTest from "./baseline-test.svelte";

  let num_questions: number = 125;
  let is_started = false;
</script>

<main>
  {#if !is_started}
    <header class="mb-6">
      <h1 class="mb-2 text-5xl font-bold">The Quizzler</h1>
      <p class="text-center text-xl">Medical Coding Edition</p>
    </header>
    <fieldset class="flex flex-col items-center justify-center gap-2">
      <label for="numquestions" class="">How many questions?</label>
      <input
        type="number"
        id="numquestions"
        min="1"
        class="pl-2 py-1 rounded"
        bind:value={num_questions}
      />

      <button class="mt-4" on:click={() => (is_started = true)}>Start</button>
    </fieldset>
  {:else}
    <BaselineTest {num_questions} />
  {/if}
</main>

<style>
</style>
