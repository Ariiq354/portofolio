<script lang="ts">
  import { Button } from '$lib/components/ui/button';
  import { Input } from '$lib/components/ui/input';
  import { Textarea } from '$lib/components/ui/textarea';
  import { House, Mail, Phone } from 'lucide-svelte';
  import emailjs from '@emailjs/browser';
  import { toast } from 'svelte-sonner';

  const info = [
    {
      icon: Phone,
      title: 'Phone',
      description: '+62 896 0583 4601'
    },
    {
      icon: Mail,
      title: 'Email',
      description: 'm.ariiq.abdillah@gmail.com'
    },
    {
      icon: House,
      title: 'Phone',
      description: 'BDB 2 Housing Complex, Block FR 9'
    }
  ];

  const sendEmail = (e: any) => {
    emailjs
      .sendForm('service_vdj986j', 'template_n4tkwdv', e.target, {
        publicKey: 'lKfN3521SPGJulGfX'
      })
      .then(
        () => {
          toast('Email sent');
        },
        (error) => {
          toast.error('Something Went Wrong');
        }
      );
  };
</script>

<section class="py-6">
  <div class="container mx-auto">
    <div class="flex flex-col gap-[30px] xl:flex-row">
      <div class="order-2 xl:order-none xl:w-[54%]">
        <form
          on:submit|preventDefault={sendEmail}
          class="flex flex-col gap-6 rounded-xl bg-[#27272c] p-10"
        >
          <h3 class="text-4xl text-accent">Let's Work Together</h3>
          <p class="text-white/60">
            I'd love to hear from you! Whether you have a question, a project in mind, or just want
            to say hello, feel free to get in touch. I'll get back to you as soon as possible.
          </p>

          <div class="grid grid-cols-1 gap-6">
            <Input name="name" placeholder="Name" class="border-white/10 focus:border-accent" />
            <Input
              name="email"
              type="email"
              placeholder="Email Address"
              class="border-white/10 focus:border-accent"
            />
            <Textarea
              name="message"
              rows={5}
              placeholder="Message"
              class="border-white/10 focus:border-accent"
            />
          </div>
          <Button
            class="max-w-40 rounded-full bg-accent text-primary hover:bg-accent/90"
            type="submit"
          >
            Send Message
          </Button>
        </form>
      </div>
      <div class="order-1 mb-8 flex flex-1 items-center xl:order-none xl:mb-0 xl:justify-end">
        <ul class="flex flex-col gap-10">
          {#each info as item, i (i)}
            <li class="flex items-center gap-6">
              <div
                class="flex aspect-square w-14 items-center justify-center rounded-md bg-[#27272c] text-accent xl:w-[72px]"
              >
                <div class="text-xl">
                  <svelte:component this={item.icon} />
                </div>
              </div>
              <div class="flex-1">
                <h3 class="text-white/60">{item.title}</h3>
                <p class="text-xl">{item.description}</p>
              </div>
            </li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
</section>
