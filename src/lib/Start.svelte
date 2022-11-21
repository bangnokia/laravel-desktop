<script lang="ts">
  import { Command } from "@tauri-apps/api/shell";
  // declare a output is an array of strings
  let output: string[] = [];
  let pid: number | null = null;

  async function start() {
    const serveCommand = new Command("artisan-serve", ["artisan", "serve"], {
      cwd: "/Users/daudau/Code/bangnokia/laravel-desktop/src-laravel",
    });
    serveCommand.stdout.on("data", (line) => {
      if (line) {
        output = [...output, line];
      }
    });
    const child = await serveCommand.spawn();
    pid = child.pid;
  }
</script>

<div>
  <div class="row">
    <button on:click={start}>Start</button>
  </div>
  <strong>Pid: {pid}</strong>
  <pre style="text-align: left">{output.join("\n")}</pre>
</div>
