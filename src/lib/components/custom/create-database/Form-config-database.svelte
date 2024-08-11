<script lang="ts">
  // shadcn-svelte
  import { Label } from "$lib/components/ui/label/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
  import { Input } from "$lib/components/ui/input";
  import * as Card from "$lib/components/ui/card/index.js";
  import { Textarea } from "$lib/components/ui/textarea/index.js";


  export let isSelectDatabase;
</script>

<Card.Root>
  <Card.Header>
    <Card.Title tag="h1" class="text-3xl">Config database</Card.Title>
    <Card.Description
      >Fill form for config your database to deployment.
    </Card.Description>
  </Card.Header>
  <Card.Content class="py-6 flex flex-col w-full md:px-20 space-y-6 ">
    <div class="flex flex-col gap-1.5">
      <Label for="name" class="font-semibold">Database Name</Label>
      <Input type="name" id="name" placeholder="Zela-database" />
    </div>
    <div class="grid w-full gap-1.5">
      <Label for="message" class="font-semibold">Description</Label>
      <Textarea placeholder="Type your message here." id="message" />
    </div>
  </Card.Content>
  <Card.Footer class="flex justify-between">
    <Button on:click={() => {
      isSelectDatabase = false;
    }}>Back</Button>
    <Button disabled>Let Built</Button>
  </Card.Footer>
</Card.Root>
