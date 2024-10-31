<script lang="ts">
    import { Input } from "$lib/components/ui/input/index.js";
    import { Label } from "$lib/components/ui/label/index.js";
  </script>

<div class="py-8 px-4 space-y-4">
  <div class="flex flex-col space-y-2">
    <h2
      class="scroll-m-20 pb-2 text-3xl font-semibold tracking-tight transition-colors first:mt-0"
    >
      Setting
    </h2>
    <p class="text-muted-foreground text-sm">Config server that you want.</p>
  </div>
  <div class="mx-8 py-8 max-h-60">
    <div class="flex w-full max-w-sm flex-col gap-1.5">
      <Label class="font-bold" for="service">Limit service</Label>
      <Input type="number" id="service" value="5" placeholder="number of service" />
      <p class="text-muted-foreground text-sm">Enter your number of limits.</p>
    </div>
  </div>
</div>
