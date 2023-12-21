<script lang="ts">
  import Layout from "./layout.svelte";
  import project from "../assets/image/project.jpg";
  import Icon from "@iconify/svelte";
  let subject: string;
  let description: string;
  const email: string = "it.aldigunawan@gmail.com";
  const contact = () => {
    const params = new URLSearchParams({
      subject,
      body: description,
    });
    window.open("mailto:".concat(email, "?", params.toString()), "_blank");
  };
</script>

<Layout id="about" title="contact">
  <div class="grid sm:grid-cols-2 grid-cols-1 gap-2">
    <div>
      <p class="text-5xl font-black text-center">
        Got project in <span class="text-blue-500">mind</span> ?
      </p>
      <img src={project} alt="project" class="h-96 mx-auto" />
      <div class="text-xs italic text-slate-300 text-center">
        <a
          href="https://www.freepik.com/free-vector/app-development-concept-illustration_12780654.htm#query=app%20development&position=1&from_view=search&track=ais&uuid=d4087ec9-db5d-48b5-90f5-b5f5b87387cc"
          >Image by storyset</a
        > on Freepik
      </div>
    </div>
    <div class="flex flex-col gap-5">
      <div>
        <p class="font-light text-sm">Subject</p>
        <input
          bind:value={subject}
          type="text"
          class="input"
          placeholder="I got project for you.."
        />
      </div>
      <div>
        <p class="font-light text-sm">Description</p>
        <textarea
          bind:value={description}
          class="input"
          placeholder="Here some ideas for my project.."
          rows="7"
        />
      </div>
      <button class="button" on:click={contact}>Send</button>
      <div
        class="flex gap-5 sm:justify-start justify-center items-center text-slate-700"
      >
        <a
          href="https://www.linkedin.com/in/aldi-gunawan-296688193/"
          target="_blank"
          title="LinkedIn"
        >
          <Icon icon="bi:linkedin" width="1.5rem" />
        </a>
        <a href="mailto:{email}" target="_blank" title="Email">
          <Icon icon="ic:round-email" width="2rem" />
        </a>
        <a href="https://t.me/aldhie33" target="_blank" title="Telegram">
          <Icon icon="ic:baseline-telegram" width="2rem" />
        </a>
      </div>
    </div>
  </div>
</Layout>

<style lang="scss">
  .input {
    @apply bg-slate-100 outline-none w-full py-2 px-4 resize-none;
  }
  .button {
    @apply bg-gradient-to-b from-blue-500 to-blue-600 text-blue-50 p-2 duration-200 active:ring-2 active:ring-blue-300 active:ring-offset-2 focus:ring-2 focus:ring-blue-300 focus:ring-offset-2;
  }
</style>
