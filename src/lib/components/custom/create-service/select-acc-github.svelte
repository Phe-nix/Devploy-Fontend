<script lang="ts">
  import * as Select from "$lib/components/ui/select";

  // SVG Icons
  import { Github } from "lucide-svelte";
</script>

<Select.Root>
  <Select.Trigger class="flex gap-2 justify-center text-card-foreground shadow-xl w-36 dark:bg-zinc-100 bg-zinc-950">
    <Github class="dark:text-zinc-950 text-zinc-100" />
    <Select.Value class="dark:text-zinc-950 text-zinc-100 placeholder-black" placeholder="Theme" />
  </Select.Trigger>
  <Select.Content>
    <Select.Item value="light">Light</Select.Item>
    <Select.Item value="dark">Dark</Select.Item>
    <Select.Item value="system">System</Select.Item>
  </Select.Content>
</Select.Root>
