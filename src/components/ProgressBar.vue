<template>
    <div class="progress">
        <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100"
            :style="{width: (quoteCount / maxQuote) * 100 + '%'}"
        >
            {{ quoteCount }} / {{ maxQuote }}
        </div>
    </div>
</template>

<script>
    export default {
        props: ["quoteCount", "maxQuote"]
    }
</script>