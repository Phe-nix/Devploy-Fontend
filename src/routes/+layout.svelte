<script>
  import "../app.scss";
  import { Toaster } from "$lib/components/ui/sonner";
  import { ModeWatcher } from "mode-watcher";
  
</script>

<Toaster position="top-center" richColors/>
<ModeWatcher />
<slot />
