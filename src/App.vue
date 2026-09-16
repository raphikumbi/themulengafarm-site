<script setup>

import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import YoutubePlayer from "./components/media/YoutubePlayer.vue";
import RaiseNowButton from "./components/buttons/RaiseNowButton.vue";
import ProjectItemCard from "./components/ProjectItemCard.vue";
import TeamMemberCard from "./components/TeamMemberCard.vue";

</script>

<template>
  <div class="min-h-screen bg-zinc-50 text-black">

    <!--
      Header bar of the site
    -->
    <Header id="header"/>

    <!--
      Website Hero
    -->
    <section id="hero">
      <img
          src="/banner.jpg"
          alt="title"
          class="w-full max-h-175 object-cover"
      />
    </section>

    <!--
      Our Mission section
    -->
    <section id="our-mission" class="max-w-content mx-auto p-5 pt-10 md:p-15">
      <div class="grid grid-cols-1 lg:grid-cols-3 items-start">

        <div class="lg:col-span-2 space-y-4 ">
          <h1 class="text-5xl md:text-6xl font-semibold tracking-wide text-black">
            Our Mission
          </h1>
          <p class="text-base text-black leading-7 text-justify md:text-left pt-5">
            TheMulengaFarm is becoming a commercial farm in Ndola, Zambia, cultivating sustainable agriculture by providing skills training and future employment opportunities for rural communities.<br>
            Our vision is to see that, through our farming activities, orphanages are supported to empower youth and vulnerable people.<br>
            We operate regenerative and sustainable citrus and crop farming, combined with our teaching activities at our Community Training Center in Ndola.<br>
            By doing so, we promote rural agricultural development, improve food security and diversification, and combat climate change by actively working against deforestation.<br>
            Our mission is not only to cultivate crops and trees but also to generate hope, create future perspectives, especially among the youth, and, by doing so, share the love of God. We look forward to seeing the agricultural sector in Zambia change.<br>
          </p>
        </div>

        <div class="space-y-3 flex flex-col justify-center pt-5 max-[1024px]:hidden">
          <div class="overflow-hidden">
            <img
                src="/logo-500.png"
                alt=""
                class="w-full h-auto max-w-82.75 mx-auto"
            />

          </div>

          <h3 class="text-sm font-bold uppercase tracking-widest text-[#A88058]  text-center">
            THE MULENGA PROJECT<br>
            FARMING GOD'S WAY
          </h3>
        </div>
      </div>

      <div class="pt-12 text-justify md:text-left">
        <p>
          <b>TheMulengaFarm (NGO)</b> is a Zambia-based NGO operating farming activities (tree nursery and fields) and teaching programs at our Community Training Center in the neighborhoods of Ndola.<br>
          <b>TheMulengaFarm (ORG)</b> is a Swiss-based registered NGO that funds and supports the work of TheMulengaFarm in Ndola, Zambia.
        </p>
      </div>
    </section>

    <!--
      Socials and Support section
    -->
    <section class=" max-w-content mx-auto pl-10 pr-10">
      <div class="flex flex-row max-[1024px]:flex-col gap-5 h-full p-5">

        <!--
          Twint
        -->
        <div class="border border-border-default flex-1 p-5 transition-all duration-300 hover:border-border-hover">
          <h3 class="mb-4 text-xl font-bold tracking-wider text-black text-center md:text-start">
            Support us via Twint
          </h3>

          <!--
            QR Code
          -->
          <div class="flex justify-center md:justify-start">
            <div class="p-5" >
              <img src="/qrcode-twint.png" alt="Twint QR Code" class="h-31 w-31 object-contain select-none"/>
            </div>
          </div>
        </div>

        <!--
          Bank Details
        -->
        <div class="border border-border-default flex-1 p-5 transition-all duration-300 hover:border-border-hover">
          <h3 class="mb-4 text-xl font-bold tracking-wider text-black text-center md:text-start">
            Bank Transfer
          </h3>

          <div class="flex flex-row ">

            <!--
              QR Code
            -->
            <div class="flex-1 flex items-center max-w-40">
              <div class="pr-5">
                <img src="/qrc-bank.png" alt="Donation QR Code" class="h-31 w-31 object-contain select-none"/>
              </div>
            </div>

            <!--
              Details
            -->
            <div class="flex-1">
              <div class="space-y-2 text-sm text-zinc-700">
                <p>
                  <b>IBAN:</b> CH34 0076 9440 8377 7200 1
                </p>
                <p>
                  <b>BANK:</b> BLKBCH22
                </p>
                <p>
                  <b>Clearing Nr:</b> 769
                </p>
                <p>
                  <b>Street:</b> Reinacherstrasse 126
                </p>
                <p>
                  <b>City:</b> Basel, CH-4053
                </p>
              </div>
            </div>
          </div>
        </div>

        <!--
          Donate Raise Now
        -->
        <div class="border border-border-default flex-1 p-5 transition-all duration-300 hover:border-border-hover">

          <div class="flex flex-col justify-between ">
            <h3 class="mb-4 text-xl font-bold tracking-wider text-black text-center md:text-start">
              Support us via RaiseNow
            </h3>

            <p class="mb-5 text-sm md:text-base text-zinc-700 leading-relaxed text-center md:text-start">
              RaiseNow is a digital fundraising platform that helps nonprofits collect donations, manage donor engagement, and process online payments efficiently.
            </p>
          </div>

          <div class="mt-auto flex justify-center md:justify-start">
            <RaiseNowButton />
          </div>

        </div>

      </div>
    </section>

    <!--
      Latest Update Section
    -->
    <section id="latest-update" class="max-w-content pl-15 pr-15 pt-10 mx-auto">
      <YoutubePlayer
          thumbnail="/video/banner-2025-christmas.jpg"
          title="Latest Update"
          id="75ftg_fsrLQ"
          duration="3:00"
          width="100%"
          height="400px"/>
    </section>

    <!--
      Current Projects and Founding
    -->
    <section id="current-projects" class="max-w-content mx-auto pl-15 pr-15 p-20">
      <h2 class="text-6xl font-semibold pt-5 pb-10">Current Projects</h2>

      <div class="grid grid-cols-1 gap-5 lg:grid-cols-2">
        <ProjectItemCard
            title="Farmland Purchase"
            description="Purchase 5–10 ha of farmland."
            :current="5000"
            :goal="100000"
        />

        <ProjectItemCard
            title="Training Center Completion"
            description="Finish construction work at the Community Training Center."
            :current="4750"
            :goal="5000"
        />

        <ProjectItemCard
            title="Water Storage Tank"
            description="5,000L tank to prevent water shortages."
            :current="0"
            :goal="500"
        />

        <ProjectItemCard
            title="Security Dog"
            description="Dog for security at the Community Training Center."
            :current="50"
            :goal="500"
        />

        <ProjectItemCard
            title="Teaching Motorcycle"
            description="Motorcycle for teaching in remote rural villages."
            :current="300"
            :goal="1500"
        />

        <ProjectItemCard
            title="Farming Materials"
            description="Fertilizer and essential farming equipment."
            :current="120"
            :goal="200"
        />

        <ProjectItemCard
            title="School Materials"
            description="Materials to support sponsored students."
            :current="40"
            :goal="50"
        />

        <ProjectItemCard
            title="Youth Microloans"
            description="Targeted microloans to empower young people."
            :current="450"
            :goal="500"
        />

        <ProjectItemCard
            title="Government Water Connection"
            description="Water connection for the community, completed in 2025."
            :current="1500"
            :goal="1500"
        />

        <ProjectItemCard
            title="School & Office Buildings"
            description="Three classrooms, an office, bathrooms and wastewater treatment, completed in 2025."
            :current="15000"
            :goal="15000"
        />

        <ProjectItemCard
            title="Water Well & Pump"
            description="Open water well with a water pump, completed in 2026."
            :current="1800"
            :goal="1800"
        />

        <ProjectItemCard
            title="Tree Planting"
            description="1,000 trees prepared for planting on the farm, completed in 2026."
            :current="800"
            :goal="800"
        />
      </div>
    </section>

    <!--
      Meet the Team
    -->
    <section id="team" class="max-w-content mx-auto pl-15 pr-15 p-20">

      <h2 class="text-6xl font-semibold pt-5 pb-10">Meet the Team</h2>

      <div class="flex justify-center">
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 w-full px-4">

          <TeamMemberCard
              imgSrc="/team/portrait-jameson.jpg"
              name="Jameson"
              func="Founder, Director"
              loc="NDOLA, ZAMBIA"
              desc="I’m passionate about my sustainable farming career, and I love transforming communities, especially supporting less privileged people in society through skills and training. I have a calling in farming, and I look forward to establishing God’s kingdom through farming God’s way. I believe that if we take care of nature, nature will take care of us."
          />

          <TeamMemberCard
              imgSrc="/team/portrait-lionel.jpg"
              name="Lionel"
              func="Founder, Networking"
              loc="BASEL, SWITZERLAND"
              desc="I look forward to seeing our culture and society develop into a more human-centered future, where sense, solidarity, communion, and beauty form its core. I love people and traveling, and I enjoy seeing the love of God made practical, starting from the ground up with a shift in agriculture."
          />

          <TeamMemberCard
              imgSrc="/team/portrait-louis.jpg"
              name="Louis"
              func="Media, Architect"
              loc="STRASBOURG, FRANCE"
              desc="I’m passionate about my career in media, and I love capturing stories through photography and visual art. I enjoy transforming perspectives and sharing moments that highlight people, culture, and everyday life, especially by giving a voice and visibility to those who are often unseen. I feel called to use media as a tool for a positive impact."
          />

          <TeamMemberCard
              imgSrc="/team/portrait-sebastian.jpg"
              name="Sebastian"
              func="Finances"
              loc="ZÜRICH, SWITZERLAND"
              desc="..."
          />

          <TeamMemberCard
              imgSrc="/team/portrait-raphael.jpg"
              name="Raphael"
              func="IT, Media"
              loc="BASEL, SWITZERLAND"
              desc="..."
          />

          <TeamMemberCard
              imgSrc="/team/portrait-francois.jpg"
              name="Francois"
              func="Landscape Architect"
              loc="ALSACE, FRANCE"
              desc="..."
          />

        </div>
      </div>
    </section>

    <br>

    <Footer />

  </div>
</template>