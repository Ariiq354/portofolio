<script lang="ts">
  const projects = [
    {
      title: 'Puskesmas Kertasemaya',
      link: '/kertasemaya.jpg',
      time: 'October 2023',
      description:
        "I created and lead the project for UPTD Puskesmas Kertasemaya's website. The website show information about profile, services, news, etc. Users can also browse a gallery showcasing their activities, and contact details for communication. It also have admin management for managing the content.",
      tech: 'NextJS, TailwindCSS, React'
    },
    {
      title: 'Tabby Talks',
      link: '/tabby.jpg',
      time: 'November 2023',
      description:
        'I created and lead the project for Tabby Talks website as a Study Project. The website a pdf scanner and analyzer using AI. Users can interact with AI Chatbot to ask about the document scanned.',
      tech: 'NextJS, TailwindCSS, OpenAI'
    },
    {
      title: 'Puskesmas Terisi',
      link: '/terisi.jpg',
      time: 'December 2023',
      description:
        "I created and lead the project for UPTD Puskesmas Terisi's website. The website show information about profile, services, news, etc. Users can also browse a gallery showcasing their activities, and contact details for communication. It also have admin management for managing the content.",
      tech: 'NextJS, TailwindCSS, React'
    },
    {
      title: 'PT. Anugrah Teknologi kecerdasan buatan',
      link: '/ptatkb.jpg',
      time: 'April 2024',
      description:
        'I help created the landing page for PT. Anugrah Teknologi Kecerdasan Buatan. It shows the profile of the company, like projects and team members.',
      tech: 'Astro, TailwindCSS, React'
    },
    {
      title: 'Keluarga Bahagia',
      link: '/kb.jpg',
      time: 'May 2024',
      description:
        "I am working on Keluarga Bahagia's website. It's a Healthy Parenting course website that sells ticket for seminar and books. Users can find the information needed on the website and also sign in to get the product.",
      tech: 'Svelte, TailwindCSS'
    },
    {
      title: 'Eduaid',
      link: '/eduaid.jpg',
      time: 'May 2024',
      description:
        "I created and lead the project for EduAid website. It's an eduaction website for school & teacher. It function as a school management system. As for teachers, they can use the tools built-in like AI Chatbot, Scoresheet scan, and Report maker.",
      tech: 'Svelte, Python, OpenAI'
    },
    {
      title: 'ERP UMKM Harijaya',
      link: '/harijaya.jpg',
      time: 'May 2024',
      description:
        "I am working on ERP website for UMKM Harijaya. It's features are debts and payments, buying, selling, stock management, and reports",
      tech: 'Svelte, TailwindCSS'
    }
  ];
</script>

<section class="w-full">
  <div class="container mx-auto">
    <div class="flex flex-col gap-4">
      <h1 class="text-center text-4xl">My Projects</h1>
      <p class="mb-12 text-center text-white/60">A showcase of my projects that i have created</p>
      <ul class="grid gap-6 md:grid-cols-2 xl:grid-cols-3">
        {#each projects as item}
          <li
            class="flex flex-col justify-between rounded-lg border-2 border-accent bg-[#232329] p-6"
          >
            <div class="flex flex-col gap-6">
              <span class="w-full rounded-sm">
                <img src={item.link} alt="" class="rounded-sm border border-accent" />
              </span>
              <div>
                <h1 class="text-xl">{item.title}</h1>
                <p class="text-accent">{item.time}</p>
                <p class="mb-4 mt-2">{item.description}</p>
              </div>
            </div>
            <div>
              <hr class="border-white/60" />
              <div class="mt-2 flex items-center gap-3">
                <span class="aspect-square w-[6px] rounded-full bg-accent"></span>
                <p class="text-white/60">{item.tech}</p>
              </div>
            </div>
          </li>
        {/each}
      </ul>
    </div>
  </div>
</section>
