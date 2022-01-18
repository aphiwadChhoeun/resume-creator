<script>
  import ResumeTitle from "./lib/ResumeTitle.svelte";
  import Headline from "./lib/Headline.svelte";

  import data from "./assets/data.json";
  import TreeView from "./lib/TreeView.svelte";
  import TreeViewItem from "./lib/TreeViewItem.svelte";
  import Contacts from "./lib/Contacts.svelte";
  import DashView from "./lib/DashView.svelte";
  import ListView from "./lib/ListView.svelte";
  import ListViewItem from "./lib/ListViewItem.svelte";
  import ThemeToggle from "./lib/ThemeToggle.svelte";

  let theme = parseInt(localStorage.getItem("theme"));
  if (theme === 1) {
    document.documentElement.classList.add("dark");
  } else {
    document.documentElement.classList.remove("dark");
  }

  const onDarkmodeClicked = (state) => {
    if (state.detail) {
      document.documentElement.classList.add("dark");
    } else {
      document.documentElement.classList.remove("dark");
    }
    localStorage.setItem("theme", state.detail ? 1 : 0);
  };
</script>

<main
  class="bg-white text-black dark:bg-neutral-900 dark:text-neutral-200 py-10 antialiased"
>
  <div class="container mx-auto md:w-6/12 sm:w-10/12 flex flex-col">
    <div class="flex flex-row justify-center">
      <ThemeToggle on:changed={onDarkmodeClicked} {theme} />
    </div>
    <ResumeTitle>{data.name}</ResumeTitle>
    <Contacts contacts={data.contacts} />
    <Headline>{data.headline}</Headline>
    <TreeView title="Experience" data={data.experience} let:item>
      <TreeViewItem {item} />
    </TreeView>
    <TreeView title="Education" data={data.education} let:item>
      <TreeViewItem {item} />
    </TreeView>
    <ListView title="Licenses & Certifications" data={data.licACerts} let:item>
      <ListViewItem {item} />
    </ListView>
    <DashView title="Skills" data={data.skills} />
    <DashView title="Languages" data={data.languages} />
  </div>
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }
</style>
