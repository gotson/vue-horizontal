# Vue Horizontal [![vue-horizontal](https://img.shields.io/npm/v/vue-horizontal.svg)](https://www.npmjs.com/package/vue-horizontal)

> An early **Beta POC** for another way to do horizontal layout in vue. Use it at your own risk.
 
### TODO
- [ ] Added relevant shields.io badges
- [ ] Onboarding banner images of the features
- [ ] All features
- [ ] More examples
- [ ] Documentation + examples github.io page
- [ ] CI Testing
- [ ] Wrappers

An ultra simple pure vue horizontal layout for modern responsive web with zero dependencies.

[![License MIT](https://img.shields.io/github/license/fuxingloh/vue-horizontal)](https://github.com/fuxingloh/vue-horizontal/blob/main/LICENSE)
[![CI Main](https://img.shields.io/github/workflow/status/fuxingloh/vue-horizontal/CI/main)](https://github.com/fuxingloh/vue-horizontal/actions?query=workflow%3ACI+branch%3Amain)
---

> SVG here of the different layout and supported features.

## Installation

```shell
npm i vue-horizontal
# or
yarn add vue-horizontal
```

## Usage
```vue
<template>
  <vue-horizontal>
    <section v-for="item in items">
      <h3>{{ item.title }}</h3>
      <p>{{ item.content }}</p>
    </section>
  </vue-horizontal>
</template>

<script>
export default {
  data() {
    return {
      items: [...Array(20).keys()].map((i) => {
        return {title: `Item ${i}`, content: `🚀 Content ${i}`};
      }),
    }
  }
}
</script>

<style scoped>
section {
  padding: 16px 24px;
  border-radius: 4px;
  background: #f5f5f5;
  margin-left: 12px;
  margin-right: 12px;
  box-sizing: border-box;
  flex-basis: calc((100% - (3 * 24px)) / 4);
}
</style>
```

<details>
<summary><b>All Features</b></summary>

```vue
<template>
  <vue-horizontal>
    <section v-for="item in items">
      {{item}}
    </section>
  </vue-horizontal>
</template>

<script>
export default {
  data() {
    return {
    }
  }
}
</script>

<style scoped>
section {
}
</style>
```
</details>

<details>
<summary><b>More Examples</b></summary>

- [ ] Link to examples/documentations?
</details>

## Features and Design Philosophy

- SSR/SSG/SPA: all modes of rendering supported
- Mobile & responsive web friendly
- Scroll bar or customizable button navigation
- Snap to the nearest item when scrolling
- Moves the responsibilities of the CSS to the user
- Extensible for any use case

## Development
Setup & develop.

```shell
npm install
npm run serve
```

## Contributions

- For any question or feature request please feel free to create an [issue](https://github.com/fuxingloh/vue-horizontal/issues/new) or [pull request](https://github.com/fuxingloh/vue-horizontal/pulls).
- For feature request, do check out the examples as some of them might have been implemented. 

## Prior art

- Airbnb.com
- [vue-horizontal-list](https://github.com/fuxingloh/vue-horizontal-list)

Originally, this project started out as another project called [vue-horizontal-list](https://github.com/fuxingloh/vue-horizontal-list).
I created the origin project because I liked how AirBnb does their horizontal layout.
I couldn't find a library that implements it vue natively without relying on a legacy js/jquery dependency.    

This project is another take on it with an ultra simple implementation that is extensible and moves the responsibility 
to the user rather than the library.
