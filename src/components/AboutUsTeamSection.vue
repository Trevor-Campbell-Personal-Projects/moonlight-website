<template>
  <div class="mx-auto max-w-5xl px-8 selection:bg-yellow-200/20 selection:text-yellow-300">
    <div class="max-w-4xl mx-auto text-center">
      <h2
        class="text-3xl sm:text-4xl mt-2 pb-0.5 font-bold font-laila text-transparent bg-clip-text bg-gradient-to-tr from-yellow-400 to-yellow-100"
      >
        The Moonlight Team
      </h2>
    </div>
    <ul role="list" class="mt-6 space-y-12 sm:divide-y sm:divide-gray-200 sm:space-y-0 lg:space-y-0">
      <li v-for="person in people" :key="person.name" class="sm:py-8">
        <div class="space-y-4 sm:grid sm:grid-cols-3 sm:items-start sm:gap-6 sm:space-y-0">
          <div class="aspect-w-3 aspect-h-2 sm:aspect-w-3 sm:aspect-h-4">
            <img
              class="object-cover shadow-lg rounded-lg sepia brightness-75 hover:filter-none"
              :src="person.imageUrl"
              alt=""
            />
          </div>
          <div class="sm:col-span-2">
            <div class="space-y-4">
              <div class="text-lg leading-6 font-medium space-y-1 text-yellow-200">
                <h3
                  class="text-2xl font-bold text-transparent bg-clip-text bg-gradient-to-t from-slate-400 via-slate-50 to-white"
                >
                  {{ person.name }}
                </h3>
                <p class="text-yellow-200/75">{{ person.role }}</p>
              </div>
              <div class="text-lg">
                <p class="text-slate-200 whitespace-pre-line">
                  {{ person.bio }}
                </p>
              </div>
              <ul role="list" class="flex space-x-5">
                <li>
                  <a :href="person.twitterUrl" class="text-slate-400 hover:text-yellow-200">
                    <span class="sr-only">Twitter</span>
                    <svg class="w-5 h-5" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20">
                      <path
                        d="M6.29 18.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0020 3.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.073 4.073 0 01.8 7.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 010 16.407a11.616 11.616 0 006.29 1.84"
                      />
                    </svg>
                  </a>
                </li>
                <li>
                  <a :href="person.linkedinUrl" class="text-slate-400 hover:text-yellow-200">
                    <span class="sr-only">LinkedIn</span>
                    <svg class="w-5 h-5" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20">
                      <path
                        fill-rule="evenodd"
                        d="M16.338 16.338H13.67V12.16c0-.995-.017-2.277-1.387-2.277-1.39 0-1.601 1.086-1.601 2.207v4.248H8.014v-8.59h2.559v1.174h.037c.356-.675 1.227-1.387 2.526-1.387 2.703 0 3.203 1.778 3.203 4.092v4.711zM5.005 6.575a1.548 1.548 0 11-.003-3.096 1.548 1.548 0 01.003 3.096zm-1.337 9.763H6.34v-8.59H3.667v8.59zM17.668 1H2.328C1.595 1 1 1.581 1 2.298v15.403C1 18.418 1.595 19 2.328 19h15.34c.734 0 1.332-.582 1.332-1.299V2.298C19 1.581 18.402 1 17.668 1z"
                        clip-rule="evenodd"
                      />
                    </svg>
                  </a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

const people = [
  {
    name: 'Trevor Campbell',
    role: 'Serial Hobby Dabbler',
    imageUrl: '/images/team-pictures/trevor-moonlight-team-pic.jpg',
    bio: 'In the moonlight, Trevor dabbles with renaissance hobbies like marble sculpting, metalworking, and leather-working. He created the Moonlight Grant to help support artists, innovators, and other creatives around the globe who don\'t have access to the same reources as others. \n\nDuring the day, he can be found playing the role of "Team Jester" at Boston-area digital health startup, Vincere Health.',
    twitterUrl: 'https://twitter.com/TrevorCampbell_',
    linkedinUrl: 'https://www.linkedin.com/in/trevordcampbell/',
  },
  // More people...
]

export default defineComponent({
  name: 'AboutUsTeamSection',
  components: {},
  setup() {
    return {
      people,
    }
  },
})
</script>
