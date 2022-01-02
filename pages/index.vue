<template>
  <div>
    <h1>Home</h1>
  </div>
</template>

<script>
const query = /* groq */ `{
  "movies": *[_type == 'movie'] {
    _id,
    title,
    "link": slug.current
  }
}
`

export default {
  name: 'MoviesList',
  asyncData({ $sanity }) {
    return $sanity.fetch(query)
  },
}
</script>
