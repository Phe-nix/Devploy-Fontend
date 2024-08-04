<script lang="ts">
  // shadcn-svelte
  import * as Card from "$lib/components/ui/card/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
  import * as ToggleGroup from "$lib/components/ui/toggle-group";

  // import components
  import CardDatabases from "./Card-databases.svelte";

  let databases = [
    {
      name: "Postgres",
      value: "postgres",
      img: "https://avatars.githubusercontent.com/u/1",
    },
    {
      name: "MongoDB",
      value: "mongodb",
      img: "https://avatars.githubusercontent.com/u/2",
    },
    {
      name: "MySQL",
      value: "mysql",
      img: "https://avatars.githubusercontent.com/u/3",
    },
    {
      name: "SQLite",
      value: "sqlite",
      img: "https://avatars.githubusercontent.com/u/4",
    },
  ];
</script>

<Card.Root>
  <Card.Header>
    <Card.Title tag="h1" class="text-3xl">Databases</Card.Title>
    <Card.Description>Select databases for deployment</Card.Description>
  </Card.Header>
  <Card.Content class="py-6">
    <div class="flex gap-4 justify-center">
      <ToggleGroup.Root variant="outline" size="xl" type="single" class="gap-6">
        {#each databases as { name, value, img }}
          <ToggleGroup.Item {value}  aria-label={name} >
            <CardDatabases name={name} img={img} />
          </ToggleGroup.Item>
        {/each}
      </ToggleGroup.Root>
    </div>
  </Card.Content>
  <Card.Footer class="flex justify-between">
    <Button disabled>Back</Button>
    <Button disabled>Let Built</Button>
  </Card.Footer>
</Card.Root>
