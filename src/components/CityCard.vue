<template>
    <div class="flex py-6 px-7 items-center bg-weather-secondary rounded-md shadow-md cursor-pointer">
        <div class="flex flex-col flex-1">
            <h2 class="text-3xl">{{city.city}}</h2>
            <h3>{{city.state}}</h3>
        </div>
        <div class="flex flex-col gap-2">
            <div class="flex flex-row gap-1">
                <img
                    class="w-[50px] h-auto"
                    :src="`http://openweathermap.org/img/wn/${city.weather.current.weather[0].icon}@2x.png`"
                    alt=""
                />
                <p class="text-3xl self-end">
                    {{Math.round(city.weather.current.temp)}}&deg;
                </p>
            </div>
            <div class="flex gap-2 self-end">
                <span class="text-xs">
                    H:
                    {{Math.round(city.weather.daily[0].temp.max)}}&deg;
                </span>
                <span class="text-xs">
                    L:
                    {{Math.round(city.weather.daily[0].temp.min)}}&deg;
                </span>
            </div>
        </div>
    </div>
</template>

<script setup>
defineProps({
    city:{
        type: Object,
        default: () => {},
    },
})
</script>