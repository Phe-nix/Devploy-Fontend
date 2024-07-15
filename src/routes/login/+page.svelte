<script lang="ts">
  // import shadcn-svelte
  import * as Card from "$lib/components/ui/card/index.js";
  import { Mail } from 'lucide-svelte';
  import { Button } from "$lib/components/ui/button/index.js";
</script>

<div
  class="h-full w-full my-44 flex flex-col items-center space-y-10 justify-center"
>
  <div class="flex flex-col space-y-10 items-center">
    <h1 class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl">
      LOGO
    </h1>
    <h1 class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl">
      Sign in to Devploy
    </h1>
  </div>
  <Card.Root class="p-28">
    <Card.Content>
      <div class="flex flex-col items-center">
        <Button class="my-2">
          <Mail class="mr-2 h-4 w-4" />
          Login with @kmitl.ac.th
        </Button>
        <p class="text-sm text-muted-foreground">Please use KMITL email to Sign in</p>
      </div>
    </Card.Content>
  </Card.Root>
</div>
