<template lang="pug">
.banner-principal
  .container.tarjeta.p-4.p-sm-5(
    :style="{'background-image': `url(${globalData.fondoBannerPrincipal})`}"
  )
    .row.justify-content-around.align-items-center
      .col-lg-7.col-xxl-6.banner-principal__info.align-items-center
        .banner-principal__programa.mb-0
          .h4.mb-0 {{globalData.nombrePrograma}}
        p Preguntas más frecuentes

      .d-none.d-lg-block.col-lg-5
        img(v-if="globalData.imagenBannerPrincipal" :src="globalData.imagenBannerPrincipal")
        .video(v-else-if="globalData.videoBannerPrincipal" v-html="globalData.videoBannerPrincipal")

</template>

<script>
import { global } from '../../config/global'
import mixins from '../../mixins/plantillaMixins'
export default {
  name: 'BannerPrincipal',
  mixins: [mixins],
  data: () => ({
    globalData: global,
  }),
}
</script>

<style lang="sass" scoped>
.banner-principal
  *
    color: $colorTextoBannerPrincipal
  p, h1
    color: $white

  .tarjeta
    background-color: $color-curso-a
    background-size: cover
    background-position: center

  &__info
    display: flex
    flex-direction: column
    justify-content: center

  &__programa
    display: flex
    align-items: center
    margin-bottom: 20px
    & > div
      text-transform: uppercase

  &__datos
    *
      line-height: 1.2em

    &__item
      display: flex
      // align-items: center
      &__titulo
        flex: 1
        text-align: right
      &__texto
        margin-top: 0.15em
        flex: 3
</style>
