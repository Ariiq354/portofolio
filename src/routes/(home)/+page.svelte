<script>
  import { Button } from '$lib/components/ui/button';
  import { Download, Github, Linkedin } from 'lucide-svelte';
</script>

<section class="h-full">
  <div class="container mx-auto h-full">
    <div class="flex flex-col items-center justify-between xl:flex-row xl:pb-24 xl:pt-8">
      <!-- Text -->
      <div class="order-2 text-center xl:order-none xl:text-left">
        <span class="text-xl">Final Year Informatics Student</span>
        <h1 class="mb-6 text-[48px] font-semibold leading-[1.1] xl:text-[80px]">
          Hello I'm <br /> <span class="text-accent">Muhammad Ariiq</span>
        </h1>
        <p class="mb-9 max-w-[500px] text-white/80">
          I'm an Informatics student with passion in web design. I am proficient in various frontend
          framework and technologies.
        </p>
        <div class="flex flex-col items-center gap-8 xl:flex-row">
          <a href="/CV.pdf" download="CV.pdf">
            <Button
              variant="outline"
              size="lg"
              class="flex items-center gap-2 rounded-full border-accent uppercase text-accent"
            >
              Download CV
              <Download size="20" />
            </Button>
          </a>
          <div class="mb-8 xl:mb-0">
            <div class="flex gap-6">
              <a
                href="https://github.com/Ariiq354"
                class="flex items-center justify-center rounded-full border border-accent p-2 text-accent transition-all duration-300 hover:bg-accent hover:text-primary"
              >
                <Github size={20} />
              </a>
              <a
                href="https://www.linkedin.com/in/muhammadariiq"
                target="_blank"
                class="flex items-center justify-center rounded-full border border-accent p-2 text-accent transition-all duration-300 hover:bg-accent hover:text-primary"
              >
                <Linkedin size={20} />
              </a>
            </div>
          </div>
        </div>
      </div>
      <!-- Photo -->
      <div class="order-1 mb-8 xl:order-none xl:mb-0">
        <div class="relative flex h-full w-full items-center justify-center">
          <div
            class="absolute flex aspect-square w-[274px] items-center justify-center overflow-hidden rounded-full xl:w-[470px]"
          >
            <img src="/fotoProfil.jpeg" alt="Profile" />
          </div>
          <svg
            class="h-[300px] w-[300px] animate-spin-slow xl:h-[506px] xl:w-[506px]"
            fill="transparent"
            viewBox="0 0 506 506"
            xmlns="http://www.w3.org/2000/svg"
          >
            <circle
              cx="253"
              cy="253"
              r="250"
              stroke="#00ff99"
              stroke-width="4"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-dasharray="24 12 2 20"
            />
          </svg>
        </div>
      </div>
    </div>
  </div>
</section>
