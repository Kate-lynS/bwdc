<script>
 
  import RightAlignedExample from "./sections/RightAlignedExample.svelte";
  import ImageExample from "./sections/ImageExample.svelte";
  import TitleSection from "./lib/TitleSection.svelte";
  import InteresectionObserverBasicExample from "./sections/IntersectionObserverBasicExample.svelte";
  import IntersectionObserverAlertExample from "./sections/IntersectionObserverAlertExample.svelte";
  import DisappearingDuckExample from "./sections/DisappearingDuckExample.svelte";
 
  import IntersectionObserverListExample from "./sections/IntersectionObserverListExample.svelte";
  
  import ScatterChart from './sections/ScatterChart.svelte';
</script>

<main>
  <TitleSection />

  <!-- Optional: Spacer or scroll trigger -->
  <section style="height: 100vh;"></section>

  <!-- Scatter chart comes *after* title -->
  <ScatterChart />

  <!-- Other storytelling sections -->
  <RightAlignedExample />
  
  <ImageExample />
  
 
  <IntersectionObserverAlertExample />
  <DisappearingDuckExample />
  <IntersectionObserverListExample />
</main>

