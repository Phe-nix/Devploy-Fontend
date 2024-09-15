<script lang="ts">
  // shadcn-svelte
  import * as Breadcrumb from "$lib/components/ui/breadcrumb/index.js";
  import * as Tabs from "$lib/components/ui/tabs";
  import * as Card from "$lib/components/ui/card/index.js";
  import { Input } from "$lib/components/ui/input/index.js";

  // import components
  import ServicesStatus from "$lib/components/custom/services-status.svelte";

  // import SVG

  // เดี๋ยวมาทำให้ดีกว่านี้55555555555
  // let thisroute = window.location.pathname;
  // let goBack = thisroute.split("/").slice(0, -2).join("/");
</script>

<div>
  <Breadcrumb.Root>
    <Breadcrumb.List>
      <Breadcrumb.Item>
        <Breadcrumb.Link href="/home">Projects</Breadcrumb.Link>
      </Breadcrumb.Item>
      <Breadcrumb.Separator />
      <Breadcrumb.Page>Zela</Breadcrumb.Page>
    </Breadcrumb.List>
  </Breadcrumb.Root>

  <div class="py-4 flex justify-between items-center">
    <h2
      class="scroll-m-20 pb-2 text-3xl font-semibold tracking-tight transition-colors first:mt-0"
    >
      Zela project
    </h2>
    <ServicesStatus status="running"/>
  </div>
</div>

<Tabs.Root value="projects" class="w-full py-6">
  <Tabs.List class="grid w-full grid-cols-3">
    <Tabs.Trigger value="projects">General</Tabs.Trigger>
    <Tabs.Trigger value="monitor">Log</Tabs.Trigger>
    <Tabs.Trigger value="setting">Setting</Tabs.Trigger>
  </Tabs.List>
  <Tabs.Content value="projects">
    <Card.Root>
      <Card.Content
        class="flex flex-row gap-3 flex-wrap items-center justify-center xl:justify-start"
      >
        Hi
      </Card.Content>
    </Card.Root>
  </Tabs.Content>
  <Tabs.Content value="password">Change your password here.</Tabs.Content>
</Tabs.Root>
