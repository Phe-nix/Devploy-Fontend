<script lang="ts">
  // shadcn-svelte
  import * as Card from "$lib/components/ui/card/index.js";
  import { Button } from "$lib/components/ui/button/index.js";

  // import components
  import SelectDatabase from "$lib/components/custom/create-database/Select-database.svelte";
  import FormConfigDatabase from "$lib/components/custom/create-database/Form-config-database.svelte";
</script>

<div class="py-2 flex flex-col">
  <h2
    class="scroll-m-20 pb-2 text-3xl font-semibold tracking-tight transition-colors first:mt-0"
  >
    Let build something new.
  </h2>
  <p class="text-muted-foreground text-sm">to deploy service</p>
</div>
<div class="px-8 py-4">
  <!-- <SelectDatabase /> -->
  <FormConfigDatabase />
</div>
