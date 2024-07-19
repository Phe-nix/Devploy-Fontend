<script lang="ts">
  // import shadcn-svelte
  import * as Card from "$lib/components/ui/card/index.js";
  import * as Tabs from "$lib/components/ui/tabs";
  import * as Command from "$lib/components/ui/command";
  import { Button } from "$lib/components/ui/button/index.js";
  import { Input } from "$lib/components/ui/input/index.js";

  // import components
  import EmptyProjects from "$lib/components/custom/emtpy-projects.svelte";

  // SVG Icons
  import { Plus } from "lucide-svelte";

  const projects = [
    {
      name: "Project 1",
      description: "Description 1",
    },
    {
      name: "Project 2",
      description: "Description 2",
    },
    {
      name: "Project 3",
      description: "Description 3",
    },
  ];
</script>

<div class="max-w-7xl mx-auto">
  <div class="flex flex-col">
    <h2
      class="scroll-m-20 pb-2 text-3xl font-semibold tracking-tight transition-colors first:mt-0"
    >
      Projects
    </h2>
    <p class="text-sm text-muted-foreground">Mannage your projects.</p>
  </div>
  <Tabs.Root value="projects" class="w-full py-10">
    <Tabs.List class="grid w-full grid-cols-4">
      <Tabs.Trigger value="projects">Projects</Tabs.Trigger>
      <Tabs.Trigger value="password">Monitor</Tabs.Trigger>
      <Tabs.Trigger value="password">Teams</Tabs.Trigger>
      <Tabs.Trigger value="password">Setting</Tabs.Trigger>
    </Tabs.List>
    <Tabs.Content value="projects">
      <Card.Root>
        <Card.Header>
          <form class="flex w-full max-w-5xl mx-auto items-center space-x-2">
            <Input
              class="shadow-lg p-4"
              type="text"
              placeholder="🔍 Search something..."
            />
            <Button class="space-x-2 flex items-center" type="submit">
              <Plus class="mr-2 size-4" />
              Create Projects
            </Button>
          </form>
        </Card.Header>
        <Card.Content>
          <EmptyProjects />
        </Card.Content>
      </Card.Root>
    </Tabs.Content>
    <Tabs.Content value="password">Change your password here.</Tabs.Content>
  </Tabs.Root>
</div>
