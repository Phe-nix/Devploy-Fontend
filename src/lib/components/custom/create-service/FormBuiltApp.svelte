<script lang="ts">
  //shadcn-svelte
  import { Input } from "$lib/components/ui/input/index.js";
  import { Label } from "$lib/components/ui/label/index.js";
  import * as Select from "$lib/components/ui/select";
  import { Textarea } from "$lib/components/ui/textarea/index.js";
  // SVG Icons
  import { Github } from "lucide-svelte";

  const stacks = [
    {
      name: "Svelte",
      label: "Svelte",
      img: "https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_svelte_icon_130157.png",
    },
    {
      name: "React",
      label: "React",
      img: "https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_reactjs_icon_130205.png",
    },
    {
      name: "Vue",
      label: "Vue",
      img: "https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_vue_icon_130078.png",
    },
    {
      name: "Angular",
      label: "Angular",
      img: "https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_angular_icon_130754.png",
    },
    {
      name: "Sapper",
      label: "Sapper",
      img: "https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_sapper_icon_130158.png",
    },
    {
      name: "Next",
      label: "Next",
      img: "https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_next_icon_130137.png",
    },
    {
      name: "Nuxt",
      label: "Nuxt",
      img: "https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_nuxt_icon_130136.png",
    },
    {
      name: "Vite",
      label: "Vite",
      img: "https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_vite_icon_130067.png",
    },
    {
      name: "Webpack",
      label: "Webpack",
      img: "https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_webpack_icon_130158.png",
    },
    {
      name: "Rollup",
      label: "Rollup",
      img: "https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_rollup_icon_130157.png",
    },
    {
      name: "Parcel",
      label: "Parcel",
      img: "https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_parcel_icon_130159.png",
    },
    {
      name: "Snowpack",
      label: "Snowpack",
      img: "https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_snowpack_icon_130156.png",
    },
  ];
</script>

<div class="flex flex-col px-5 space-y-2">
  <div
    class="flex gap-2 my-4 justify-center rounded-lg border text-card-foreground shadow-xl w-28 py-2 dark:bg-zinc-100 bg-zinc-950"
  >
    <Github class="dark:text-zinc-950 text-zinc-100" />
    <p class="dark:text-zinc-950 text-zinc-100">Phe-nix</p>
  </div>
  <form class="space-y-4 w-full">
    <div class="flex flex-col gap-1.5">
      <Label for="email-2">Service name</Label>
      <Input
        type="email"
        id="email-2"
        placeholder="Service name"
        value="Zela-Fontend"
      />
    </div>
    <div class="flex flex-col gap-1.5">
      <Label for="email-2">Framework preset</Label>
      <Select.Root portal={null}>
        <Select.Trigger>
          <Select.Value placeholder="Select a Framework" />
        </Select.Trigger>
        <Select.Content>
          {#each stacks as stack}
            <Select.Item value={stack.name} label={stack.label}
              >{stack.label}</Select.Item
            >
          {/each}
        </Select.Content>
        <Select.Input name="favoriteFruit" />
      </Select.Root>
    </div>
    <div class="grid gap-1.5">
        <Label for="message">Description</Label>
        <Textarea placeholder="Type your message here." id="message" />
      </div>
  </form>
</div>
