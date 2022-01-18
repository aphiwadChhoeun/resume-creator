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
  import Note from "./lib/Note.svelte";

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
  class="bg-white text-black dark:bg-neutral-900 dark:text-neutral-200 py-10 antialiased print:py-0"
>
  <div class="container mx-auto md:w-6/12 sm:w-10/12 flex flex-col">
    <div class="flex flex-row justify-center print:invisible">
      <ThemeToggle on:changed={onDarkmodeClicked} {theme} />
    </div>
    <ResumeTitle>{data.name}</ResumeTitle>
    <Contacts contacts={data.contacts} />
    <Headline>{data.headline}</Headline>
    <TreeView title="Experience" data={data.experience} let:item>
      <span slot="icon" class="pr-2">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M21 13.255A23.931 23.931 0 0112 15c-3.183 0-6.22-.62-9-1.745M16 6V4a2 2 0 00-2-2h-4a2 2 0 00-2 2v2m4 6h.01M5 20h14a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
          />
        </svg>
      </span>

      <TreeViewItem {item} />
    </TreeView>
    <TreeView title="Education" data={data.education} let:item>
      <span slot="icon" class="pr-2">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path d="M12 14l9-5-9-5-9 5 9 5z" />
          <path
            d="M12 14l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14z"
          />
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M12 14l9-5-9-5-9 5 9 5zm0 0l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14zm-4 6v-7.5l4-2.222"
          />
        </svg>
      </span>

      <TreeViewItem {item} />
    </TreeView>
    <ListView title="Licenses & Certifications" data={data.licACerts} let:item>
      <span slot="icon" class="pr-2">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z"
          />
        </svg>
      </span>

      <ListViewItem {item} />
    </ListView>
    <DashView title="Skills" data={data.skills} />
    <DashView title="Languages" data={data.languages} />
    <Note note={data.note} />
  </div>
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }
</style>
