# vue-gallery

A one-page, photography portfolio website built with Nuxt.js featuring lazy-loaded images.

[Live Site](https://vue-gallery-seven.vercel.app/)

![](https://github.com/stormcloud266/vue-gallery/blob/master/screenshot.gif)

## Challenges and Goals
* Gain working knowledge of Vue and Nuxt
* Connect a Nuxt site to a headless cms
* Implement lazy loaded images

## Solutions

My main goal with this project was to gain some experience working with Vue. I used Nuxt to generate a static site and Vercel for hosting. 

I wanted to connect the site to a headless cms, and I decided on DatoCMS because of their great image API. The data is fetched from the cms using GraphQL.

## Project Details
* front end: [Nuxt.js](https://nuxtjs.org/)
* content management: [DatoCMS](https://www.datocms.com/)
* hosting: [Vercel](https://vercel.com/)

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).
