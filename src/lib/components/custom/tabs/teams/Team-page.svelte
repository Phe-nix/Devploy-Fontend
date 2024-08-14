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
    <form class="flex w-full max-w-5xl mx-auto space-x-4">
      <Input
      class="shadow-lg p-4"
      type="text"
      placeholder="🔍 Search something..."
      />
      <ModalCreateTeam />
    </form>
  </Card.Header>
  <Card.Content>
    <CardTeams />
  </Card.Content>
</Card.Root>
