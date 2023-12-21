<script lang="ts">
  import Icon from "@iconify/svelte";
  import Layout from "./layout.svelte";
  const services = [
    {
      title: "Multifunctional Application",
      icon: "grommet-icons:services",
      desc: "I build versatile web applications with multifunctional capabilities, ensuring a seamless and user-friendly experience tailored to your needs.",
    },
    {
      title: "Backend Application",
      icon: "solar:server-minimalistic-broken",
      desc: "Elevate your digital presence with my powerful backend solutions, ensuring seamless functionality and a standout user experience.",
    },
    {
      title: "Mobile Application",
      icon: "fluent-mdl2:mobile-report",
      desc: "Unlock your business potential with my React Native expertise, ensuring standout mobile apps that blend efficiency and innovation for seamless performance and user appeal.",
    },
    {
      title: "Company Profile",
      icon: "mdi:company",
      desc: "Elevate your brand with my company profile web service—captivating, engaging, and uniquely yours.",
    },
  ];
</script>

<Layout title="services" id="services">
  <div class="grid sm:grid-cols-4 grid-cols-1 gap-5">
    {#each services as service}
      <div class="bg-gradient-to-b from-slate-100 to-slate-200 p-5">
        <Icon icon={service.icon} class="text-4xl mb-2" />
        <p class="font-semibold">{service.title}</p>
        <small>
          {service.desc}
        </small>
      </div>
    {/each}
  </div>
</Layout>
