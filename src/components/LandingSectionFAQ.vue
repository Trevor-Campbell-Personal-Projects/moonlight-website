<!-- This example requires Tailwind CSS v2.0+ -->
<template>
  <div class="max-w-7xl mx-auto px-8 selection:bg-yellow-200/20 selection:text-yellow-300">
    <div class="max-w-3xl mx-auto divide-y-4 divide-slate-800">
      <h2
        class="text-center mt-2 -mb-1.5 pb-1.5 text-3xl sm:text-4xl font-laila font-semibold tracking-tight text-transparent bg-clip-text bg-gradient-to-tr from-yellow-400 to-yellow-100"
      >
        Frequently Asked Questions
      </h2>
      <dl class="mt-6 space-y-6 divide-y-2 divide-slate-900">
        <Disclosure v-for="faq in faqs" :key="faq.question" v-slot="{ open }" as="div" class="pt-6">
          <dt class="text-lg">
            <DisclosureButton
              class="text-left w-full flex justify-between items-start text-gray-400 focus:outline-none focus:ring-2 focus:ring-offset-4 focus:ring-offset-black focus:ring-yellow-200 focus:rounded-md"
            >
              <span
                :class="[
                  open
                    ? 'text-xl font-laila font-medium tracking-tight text-transparent bg-clip-text bg-gradient-to-tr from-yellow-400 to-yellow-100'
                    : 'text-xl font-medium font-laila tracking-tight text-slate-100',
                ]"
              >
                {{ faq.question }}
              </span>
              <span class="ml-6 h-7 flex items-center">
                <ChevronDownIcon
                  :class="[open ? '-rotate-180 text-yellow-200' : 'rotate-0', 'h-6 w-6 transform']"
                  aria-hidden="true"
                />
              </span>
            </DisclosureButton>
          </dt>
          <transition
            enter-active-class="transition duration-200 ease-in-out"
            enter-from-class="transform scale-95 opacity-0"
            enter-to-class="transform scale-100 opacity-100"
            leave-active-class="transition duration-75 ease-in-out"
            leave-from-class="transform scale-100 opacity-100"
            leave-to-class="transform scale-95 opacity-0"
          >
            <DisclosurePanel as="dd" class="mt-2 pr-12">
              <p class="text-base text-slate-100">
                {{ faq.answer }}
              </p>
            </DisclosurePanel>
          </transition>
        </Disclosure>
      </dl>
    </div>
  </div>
</template>

<script lang="ts">
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'
import { ChevronDownIcon } from '@heroicons/vue/outline'

import { defineComponent } from 'vue'

const faqs = [
  {
    question: 'Who should apply for a Moonlight Grant?',
    answer:
      "Moonlight Grants are intended for any and all creatives and innovators. If you're a Creator, Hacker, Artist, Builder, Musician, Designer, Craftsman, Filmmaker, Chef, etc – you should apply! Not quite sure you qualify? You should apply anyways! We love to support those pushing the envelope and learning all kinds of new skills.",
  },
  {
    question: 'How much $$$ can I get?',
    answer:
      'Most Moonlight Grants are awards of $200 – $1,000 USD. Amounts awareded to grant recipients vary based on the assesed need of each application duirng the review process.',
  },
  {
    question: 'Are there any strings attached if I receive a grant?',
    answer:
      'Nope! No strings attached at all! However, we do ask that you put your grant toward furthering your project, education, hobby, or side hustle stated in your application. We also love it when grant recipients keep us up to date – feel free to share your progress with us on Twitter!',
  },
  {
    question: "What if I'm not selected for a grant?",
    answer:
      'Regardless of the outcome, our team will contact you with the decision of your application. If you are not selected, we encourage you to apply for the next batch of Moonlight Grants when enrollment re-opens!',
  },
  {
    question: 'What can I use my grant money for?',
    answer:
      'Moonlight Grant awards can be used toward anything that will help you reach your project goals stated in your application. But we do require that grant money be used for those purposes.',
  },
  {
    question: "How can I receive my grant money if I'm selected?",
    answer:
      "We recognize that everybody has different. If you're located in the United States, we support Crypto, CashApp, Venmo, Digital Gift Card, or Direct Deposit to your Bank Account. For international recipients, we are only able to deliver grant rewards via crypto at this time. If you're not sure how to accept crypto, we'll gladly help you get set up!",
  },
  // More questions...
]

export default defineComponent({
  name: 'LandingSectionFAQ',
  components: {
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
    ChevronDownIcon,
  },
  setup() {
    return {
      faqs,
    }
  },
})
</script>
