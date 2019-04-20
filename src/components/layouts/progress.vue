<template>
      <div class="progress" style="border-radius: none;">
            <div class="progress-bar" role="progressbar" :style="{ width: quotesCount/maxCount * 100 + '%'}" style="border-radius: none;" :aria-valuenow="quotesCount" aria-valuemin="0" aria-valuemax="100">
                  {{quotesCount}} / {{maxCount}}
            </div>
      </div>
</template>

<script>
      export default {
            props: ['quotesCount', 'maxCount']
      }
</script>
