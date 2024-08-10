<script lang="ts">
  // shadcn-svelte
  import * as Card from "$lib/components/ui/card";
  import { Input } from "$lib/components/ui/input/index.js";

  // import components
  import ModalCreateTeam from "./ModalCreateTeam.svelte";
  import CardTeams from "./Card-teams.svelte";

</script>

<Card.Root>
  <Card.Header>
    <form class="flex flex-col w-full max-w-5xl mx-auto space-y-4">
      <div class="flex justify-between">
        <div>
          <h2 class="text-3xl font-semibold tracking-tight transition-colors first:mt-0">
            Teams
          </h2>
          <p class="text-muted-foreground text-sm">Mannage your teams.</p>
        </div>
        <ModalCreateTeam />
      </div>
      <Input
        class="shadow-lg p-4"
        type="text"
        placeholder="🔍 Search something..."
      />
    </form>
  </Card.Header>
  <Card.Content>
    <CardTeams />
  </Card.Content>
</Card.Root>
