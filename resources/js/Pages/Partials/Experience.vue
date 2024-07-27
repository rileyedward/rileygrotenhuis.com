<script setup>
const experiences = [
  {
    color: 'blue-500',
    timeline: 'Nov 2021 - Aug 2024',
    position: 'Software Engineer',
    company: 'Midwestern Interactive',
    technology:
      'Php, Laravel, JavaScript, TypeScript, Vue, Next.js, Docker, Digital Ocean, and more.',
    details: [
      'Designed and developed software for an analytics marketing platform, creating efficient ETL pipelines to integrate data from various sources and enabling seamless data analysis.',
      'Engineered software solutions for an alternative school lunch program, efficiently handling thousands of real time transactions daily across numerous schools on the East Coast.',
      'Led a development team, conducting regular meetings to support professional growth and skill enhancement, which boosted team performance and improved project outcomes.',
    ],
  },
  {
    color: 'red-500',
    timeline: 'Jan 2020 - Nov 2021',
    position: 'Web Developer',
    company: 'Missouri State University',
    technology: 'C#, JavaScript, Python, Asp.NET, and React',
    details: [
      'Collaborated with developers, designers, and content strategists to deliver digital solutions for the\n' +
        'university s extensive community of students, faculty, and staff.',
      'Utilized scripting and external APIs to successfully migrate tens of thousands of digital assets\n' +
        'between CMS platforms, significantly reducing manual effort and saving time.',
      'Partnered with the music department to create an online repository for master s students, enabling\n' +
        'them to publish and showcase multi medium thesis projects.',
    ],
  },
];
</script>

<template>
  <div
    class="max-w-6xl mx-auto py-24 px-8 flex flex-col-reverse md:flex-row gap-8 md:gap-0 justify-between items-center"
  >
    <div class="flex flex-col gap-36">
      <!-- Experience -->
      <div
        v-for="(experience, index) in experiences"
        :key="index"
        class="flex flex-col md:flex-row gap-20"
      >
        <!-- Overview -->
        <div class="w-full md:w-1/2">
          <!-- Timeline -->
          <div class="text-base font-semibold text-gray-300 mb-8">
            {{ experience.timeline }}
          </div>

          <div class="mb-8">
            <!-- Position -->
            <h3 class="text-3xl font-bold mb-1">{{ experience.position }},</h3>
            <!-- Company -->
            <h5 :class="`text-3xl text-${experience.color} font-bold`">
              {{ experience.company }}
            </h5>
          </div>

          <!-- Technologies -->
          <div>
            <p class="text-gray-400 font-semibold">
              {{ experience.technology }}
            </p>
          </div>
        </div>

        <!-- Description -->
        <div class="w-full md:w-1/2">
          <ul class="flex flex-col gap-8">
            <li
              v-for="(detail, index) in experience.details"
              :key="index"
              class="text-gray-50 leading-loose"
            >
              {{ detail }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>
