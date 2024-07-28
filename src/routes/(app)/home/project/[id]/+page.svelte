<script lang="ts">
  // shadcn-svelte
  import * as Breadcrumb from "$lib/components/ui/breadcrumb/index.js";
  import * as Card from "$lib/components/ui/card/index.js";
  import { Input } from "$lib/components/ui/input/index.js";

  // import components
  import EmptyProjects from "$lib/components/custom/Emtpy-projects.svelte";
  import CardProjects from "$lib/components/custom/Card-projects.svelte";
  import DropdownCreateService from "$lib/components/custom/Dropdown-create-service.svelte";
  // SVG Icons

  // let service = [
  //   {
  //     name: "Zela-Frontend",
  //     time: "21",
  //     img: "https://github.com/Phe-nix.png",
  //     linkGit: "Phe-nix/zela",
  //   },
  // ];

  let services = {
    app: [
      {
        name: "Zela-Frontend",
        time: "21",
        img: "https://github.com/Phe-nix.png",
        linkGit: "Phe-nix/zela",
        stack: "Svelte",
      },
    ],
    database: [
      {
        name: "Zela-database",
        time: "21",
        stack: "MongoDB",
      },
    ],
  };
</script>

<div>
  <Breadcrumb.Root>
    <Breadcrumb.List>
      <Breadcrumb.Item>
        <Breadcrumb.Link href="/home">Projects</Breadcrumb.Link>
      </Breadcrumb.Item>
      <Breadcrumb.Separator />
      <Breadcrumb.Item>
        <Breadcrumb.Page>Project Name</Breadcrumb.Page>
      </Breadcrumb.Item>
    </Breadcrumb.List>
  </Breadcrumb.Root>

  <div class="py-6 flex justify-between items-center">
    <h2
      class="scroll-m-20 pb-2 text-3xl font-semibold tracking-tight transition-colors first:mt-0"
    >
      Projects Name
    </h2>
    <DropdownCreateService />
  </div>
  <Card.Root>
    <Card.Header>
      <form class="flex w-full max-w-5xl mx-auto items-center space-x-2">
        <Input
          class="shadow-lg p-4"
          type="text"
          placeholder="🔍 Search something..."
        />
      </form>
    </Card.Header>
    <Card.Content>
      {#if services == undefined}
        <EmptyProjects type="service" />
      {:else}
        <div class="my-2">
          <h2
            class="scroll-m-20 pb-4 text-3xl font-semibold tracking-tight transition-colors first:mt-0"
          >
            Applications ({services.app.length})
          </h2>
          <div
            class="flex flex-row gap-3 flex-wrap items-center justify-center xl:justify-start"
          >
            {#each services.app as service}
              <CardProjects type="service" {service} />
            {/each}
          </div>
        </div>
        <div class="py-4">
          <h2
            class="scroll-m-20 pb-4 text-3xl font-semibold tracking-tight transition-colors first:mt-0"
          >
            Databases ({services.database.length})
          </h2>
          <div
            class="flex flex-row gap-3 flex-wrap items-center justify-center xl:justify-start"
          >
            {#each services.database as service}
              <CardProjects type="service" {service} />
            {/each}
          </div>
        </div>
      {/if}
    </Card.Content>
  </Card.Root>
</div>
