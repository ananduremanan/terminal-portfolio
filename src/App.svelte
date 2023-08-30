<script lang="ts">
  let logs = [
    "Loading Awesome Portfolio...",
    "Who Im I?",
    "Loading answer..",
    "React Developer, 3D Artist, Beat Maker Cinephile",
    "Techs I know!",
    "Loading answer..",
    "React.JS(Next.Js, React Redux), Svelte, Tailwind CSS, Rust",
  ];

  let showCursor = true;

  setInterval(() => {
    showCursor = !showCursor;
  }, 100);

  let currentLogIndex = 0;
  let currentCharIndex = 0;
  setInterval(() => {
    if (currentLogIndex < logs.length) {
      if (currentCharIndex < logs[currentLogIndex].length) {
        currentCharIndex++;
      } else {
        currentLogIndex++;
        currentCharIndex = 0;
      }
    }
  }, 100);
</script>

<main class="">
  <div>
    <div class="card p-4 w-screen h-screen">
      {#each logs as log, i}
        {#if i < currentLogIndex}
          <p class="text-green-400"><span>C:\User\Anandhu\Portfolio > </span>{log}</p>
        {:else if i === currentLogIndex}
          <p class="text-green-400">
            {log.slice(
              0,
              currentCharIndex
            )}{#if showCursor && i === logs.length - 1 && currentCharIndex === log.length}_{/if}
          </p>
        {/if}
      {/each}
    </div>
  </div>
</main>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Finlandica:wght@700&display=swap");

  h1 {
    font-family: "Finlandica", sans-serif;
  }

  .card {
    background-color: black;
    border-radius: 1rem;
    font-family: monospace;
  }
</style>
