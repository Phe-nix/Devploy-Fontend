<script lang="ts">
  // shadcn-svelte
  import * as Card from "$lib/components/ui/card/index.js";
  import { Button } from "$lib/components/ui/button/index.js";

  // import components
  import GithubConnect from "$lib/components/custom/create-service/GithubConnect.svelte";
  import SelectRepo from "$lib/components/custom/create-service/SelectRepo.svelte";
  import FormBuiltApp from "$lib/components/custom/create-service/FormBuiltApp.svelte";
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
  <Card.Root>
    <Card.Header>
      <Card.Title tag="h1">Import Application</Card.Title>
      <Card.Description
        >Import project to deployment with Github</Card.Description
      >
    </Card.Header>
    <Card.Content class="py-10">
      <!-- <GithubConnect /> -->
      <!-- <SelectRepo /> -->
      <FormBuiltApp />
    </Card.Content>
    <Card.Footer class="flex justify-between">
      <Button disabled>Back</Button>
      <Button disabled>Let Built</Button>
    </Card.Footer>
  </Card.Root>
</div>
