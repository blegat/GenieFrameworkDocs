<script setup>
const contentQuery = await queryContent('tutorials/').sort(
    { timestamp: -1, }
).find()
</script>

<template>
    <Container>
        <div class="relative min-h-[89vh]">
            <div class="pt-12">
                <div class="xl:container m-auto px-6 text-gray-600 md:px-12 xl:px-6">
                    <div class="mb-20 space-y-2 text-center">
                        <h2 class="text-3xl font-bold text-gray-800 md:text-7xl dark:text-white">
                            Written tutorials
                        </h2>
                        <p class="lg:mx-auto lg:w-7/12 text-gray-600 dark:text-gray-300 text-2xl">
                            Learn to build Genie apps step by step
                        </p>
                    </div>
                </div>
                <div class="grid gap-8 sm:grid-cols-2 xl:grid-cols-3 mx-4 pb-12">
                    <CardGrid>
                        <FlowCard v-for="post in contentQuery" :post="post" :key="post._id" />
                    </CardGrid>
                </div>
            </div>
        </div>
        <div class="relative min-h-[89vh]">
            <div class="pt-12">
                <div class="xl:container m-auto px-6 text-gray-600 md:px-12 xl:px-6">
                    <div class="mb-20 space-y-2 text-center">
                        <h2 class="text-3xl font-bold text-gray-800 md:text-7xl dark:text-white">
                            Video tutorials
                        </h2>
                        <p class="lg:mx-auto lg:w-7/12 text-gray-600 dark:text-gray-300 text-2xl">
                            For visual learners
                        </p>
                    </div>
                </div>
                <div class="grid gap-8 sm:grid-cols-2 xl:grid-cols-3 mx-4 pb-12">
                    <CardGrid>
                        <VideoCard v-for="post in contentQuery" :post="post" :key="post._id" />
                    </CardGrid>
                </div>
            </div>
        </div>
    </Container>
</template>

