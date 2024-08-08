<script setup>
import GitHubIcon from '@/Components/Icons/GitHubIcon.vue';
import { ref, watch } from 'vue';

watch(() => {
  setInterval(() => {
    nextProject();
  }, 15000);
});

const projects = ref([
  {
    title: 'Corvesive',
    href: 'https://github.com/rileyedward/corvesive',
    github: 'https://github.com/rileyedward/corvesive',
    slogan: 'Simplify your budgeting.',
    tech: 'PHP, Laravel, MySQL, JavaScript, Vue.js, TailwindCSS, Docker',
    description: [
      'Corvesive is an online application designed to simplify your budgeting. Track your income by uploading pay stubs, record your monthly expenses, and effortlessly monitor where your money is going and how much you have left. Gain clarity on your financial situation to make better budgeting decisions.',
      'With Corvesive, you can effortlessly track your monthly income by uploading your pay stubs. Whether you’re paid weekly, bi-weekly, or monthly, Corvesive accommodates various payment intervals, ensuring an accurate reflection of your earnings. The application will categorize and sum up your income over different periods, helping you to stay on top of your finances and plan effectively.',
      'Whether it’s a recurring payment like rent, a budgeted amount for groceries, or the funds you’re setting aside for savings, Corvesive makes it easy to track all your monthly expenses. Schedule future expenses to manage your cash flow more precisely and stay organized with upcoming due dates.',
      'For a clearer view of your remaining budget, use Transactions in Corvesive to record bills you pay, money you deposit, or any other payments you make. Your dashboard will display recent transactions and provide a summary of your budget’s surplus values. Easily track your spending and deposits over time to better manage your financial health and make more informed decisions.',
    ],
  },
  {
    title: 'Applicy',
    href: 'https://applicy.rileyedward.com',
    github: 'https://github.com/rileyedward/applicy',
    slogan: 'Streamline your job application journey.',
    tech: 'PHP, Laravel, MySQL, JavaScript, Vue.js, TailwindCSS, Docker, OpenAI, AI',
    description: [
      'Applicy is a comprehensive online platform that simplifies your job application process. Create a personalized profile to seamlessly track all your job applications and monitor their progress in real time. With Applicy, you can easily organize your job search efforts, making it simpler to stay on top of your applications and secure your next opportunity.',
      'With our application management system, you can effortlessly store and organize all your job applications in one convenient location. Simply add a new application by filling in essential details such as the job title, company name, and job URL. You can also include an overview of the job description to better understand the role’s requirements.',
      'Once you’ve created an application, you can easily update its progress to track its lifecycle over time. This feature allows you to stay organized and monitor the status of your applications throughout your job search.',
      'Harness the power of our AI Assistant, powered by OpenAI, to generate a variety of resources and messages designed to enhance your job search experience. Currently, the AI Assistant can create cover letters and follow-up messages, but the possibilities for future resources are endless. Stay tuned for even more features that will further streamline and support your job hunt!',
    ],
  },
  {
    title: 'rbranch',
    href: 'https://github.com/rileyedward/rbranch',
    github: 'https://github.com/rileyedward/rbranch',
    slogan: 'CLI tool built to simplify git branches.',
    tech: 'Go, Bubbletea, Git',
    description: [
      'rbranch is a powerful CLI tool built with Go and Bubble Tea, designed to streamline your Git workflow by simplifying branch management. Whether you’re tired of typing out long branch names or just want to make your Git experience more efficient, rbranch has you covered.',
      'With rbranch, you can quickly checkout branches, copy branch names to your clipboard, and delete branches, all with just a few commands. The tool presents a user-friendly interface for selecting branches, making these common Git operations quicker and less error-prone.',
      'Installation is straightforward, requiring just a few steps to set up the tool on your system. Once installed, you can use commands like `rbranch` to list and checkout branches, `rbranch -c` to copy branch names, and `rbranch -d` to delete them, all from the comfort of your terminal.',
      'rbranch is perfect for developers who want to save time and avoid the hassle of manually managing branches in Git. It’s a lightweight, efficient solution that integrates seamlessly into your existing workflow, making it easier than ever to stay focused on coding.',
    ],
  },
  {
    title: 'AirQueue',
    href: 'https://github.com/rileyedward/airqueue',
    github: 'https://github.com/rileyedward/airqueue',
    slogan: 'Share music with your friends using Live Sessions!',
    tech: 'PHP, Laravel, MySQL, JavaScript, Vue.js, TailwindCSS, Docker',
    description: [
      "AirQueue is a platform designed to enhance your music-sharing experience with friends through interactive Live Sessions. Integrating seemlessly with the Spotify Developer API to search for songs, as well as interact with the user's Spotify account.",
      'Start or join a Live Session using a Session ID and an optional passcode to share music with others. You can view incoming song requests from other participants and search for songs to request from them.',
      'Bands in AirQueue make it easy to share music and start Live Sessions with friends. You can join a Band via an invitation from the owner or create your own Band and invite others to share music together',
      'When you receive a song request, you can choose to approve or deny it. Denying a request removes it from your queue, while approving a request adds the song to your live Spotify player’s queue.',
    ],
  },
]);

const focusedProject = ref(0);

const nextProject = () => {
  focusedProject.value =
    focusedProject.value === projects.value.length - 1
      ? 0
      : focusedProject.value + 1;
};
</script>

<template>
  <div class="w-full py-24">
    <div class="max-w-6xl mx-auto px-8">
      <div class="flex flex-col-reverse md:flex-col gap-2">
        <!-- Project -->
        <div class="min-h-fit md:min-h-[500px]">
          <transition name="fade" mode="out-in">
            <div
              :key="focusedProject"
              class="flex items-center justify-between mb-2"
            >
              <!-- Details -->
              <div class="max-w-[285px] md:max-w-full">
                <a :href="projects[focusedProject].href" target="_blank">
                  <h3 class="text-4xl font-extrabold text-red-500">
                    {{ projects[focusedProject].title }}
                  </h3>
                </a>
                <p class="text-lg text-gray-300">
                  {{ projects[focusedProject].slogan }}
                </p>
              </div>

              <a :href="projects[focusedProject].github" target="_blank">
                <GitHubIcon />
              </a>
            </div>
          </transition>

          <!-- Technology -->
          <transition name="fade" mode="out-in">
            <p :key="focusedProject" class="text-gray-400 mb-6">
              {{ projects[focusedProject].tech }}
            </p>
          </transition>

          <!-- Description -->
          <transition name="fade" mode="out-in">
            <div :key="focusedProject" class="space-y-6">
              <p
                v-for="(paragraph, index) in projects[focusedProject]
                  .description"
                :key="index"
                class="text-gray-100"
              >
                {{ paragraph }}
              </p>
            </div>
          </transition>
        </div>

        <!-- Project Dot Switcher -->
        <div class="flex justify-center">
          <div
            v-for="(project, index) in projects"
            :key="index"
            @click="focusedProject = index"
            :class="{
              'w-4 h-4 bg-red-500 rounded-full mx-2 cursor-pointer':
                focusedProject === index,
              'w-4 h-4 bg-gray-500 rounded-full mx-2 cursor-pointer':
                focusedProject !== index,
            }"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
  opacity: 0;
}
</style>
