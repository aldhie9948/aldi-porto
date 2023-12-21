<script lang="ts">
  import Icon from "@iconify/svelte";
  import work1 from "../assets/image/projects/work1.png";
  import work2 from "../assets/image/projects/work2.png";
  import work3 from "../assets/image/projects/work3.png";
  import Layout from "./layout.svelte";

  const works = [
    {
      projectName: "Relawan Center",
      image: work1,
      description:
        "An application for surveying volunteers is one of the potential candidates within the scope of districts, electoral districts, sub-districts, and neighborhoods.",
      tools: [
        { icon: "ri:svelte-fill", name: "Svelte" },
        { icon: "mdi:google-maps", name: "Google Maps API" },
        { icon: "simple-icons:pocketbase", name: "Pocketbase" },
        { icon: "simple-icons:tailwindcss", name: "Tailwindcss" },
        { icon: "teenyicons:python-outline", name: "Python" },
      ],
    },
    {
      projectName: "SPM Company Profile",
      image: work2,
      description:
        "The profile website of Sakha Pratama Mandiri, a company operating in the field of elevators and escalators, and collaborating with international companies.",
      tools: [
        { icon: "mdi:react", name: "React" },
        { icon: "simple-icons:tailwindcss", name: "Tailwindcss" },
      ],
    },
    {
      projectName: "JETAR Local Courier Management",
      image: work3,
      description:
        "A multifunctional application such as checking shipping costs, tracking delivery status, daily reporting, and attendance for the local JETAR courier operations, integrated with the driver's smartphone application.",
      tools: [
        { icon: "mdi:react", name: "React" },
        { icon: "teenyicons:nextjs-outline", name: "NextJS" },
        { icon: "mdi:google-maps", name: "Google Maps API" },
        { icon: "simple-icons:tailwindcss", name: "Tailwindcss" },
        { icon: "simple-icons:mongodb", name: "MongoDB" },
      ],
    },
  ];
</script>

<Layout id="work" title="recent works">
  <div class="grid sm:grid-cols-3 grid-cols-1 gap-5">
    {#each works as work, i (i)}
      <div>
        <img src={work.image} alt={work.image.toString()} class="thumbnail" />
        <div class="font-light grid grid-cols-1 gap-1.5">
          <div>
            <small class="font-bold">Project name</small>
            <p>{work.projectName}</p>
          </div>
          <div>
            <small class="font-bold">Description</small>
            <p>{work.description}</p>
          </div>
          <div>
            <small class="font-bold">Tools</small>
            {#each work.tools as item}
              <div class="flex gap-2 items-center">
                <Icon icon={item.icon} />
                <p>{item.name}</p>
              </div>
            {/each}
          </div>
        </div>
      </div>
    {/each}
  </div>
</Layout>

<style lang="scss">
  .thumbnail {
    @apply border-2 border-slate-800 mb-3 shadow-md hover:scale-105 duration-200;
  }
</style>
