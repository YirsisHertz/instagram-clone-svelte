<script>
  import { onMount } from "svelte";

  import Header from "./components/Header.svelte";
  import Main from "./components/Main.svelte";
  import Sidebar from "./components/Sidebar.svelte";
  import TimeLine from "./components/TimeLine.svelte";

  let data = {};

  onMount(async () => {
    const res = await fetch(
      "https://us-central1-pugstagram-co.cloudfunctions.net/data"
    );
    data = await res.json();
  });
</script>

<div class="App">
  <Header />
  <Main>
    <TimeLine posts={data?.posts} />
    <Sidebar {...data?.user} />
  </Main>
</div>

<style>
  :global(body) {
    background-color: #fafafa;
    color: rgba(38, 38, 38, 0.7);
    margin: 0;
    padding: 0;
  }

  :global(h1, h2, h3) {
    margin: 0;
    padding: 0;
  }
</style>
