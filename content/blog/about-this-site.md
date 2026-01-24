---

title: 'About This Site'
description: 'A look behind the technologies and inspiration for this site'
date: '20-07-2024'
id: 2
tags: 'Programming'

---


So i guess this is the first proper post for my site where i will explain how the tech works for this site (mostly so i dont forget XD)

## Tech Stack

- **Framework:** I've made this evrsion of my website with Nuxt.js which is a framework based on Vue.js
- **Hosting:** The site is hosted on Vercel within the free teir
- **Domain Management:** I put the domain on cloudflare for now at least

### Markdown Formatting

This was a pain to setup, kinda, i got stuck for ages because i didnt realise **the paths for the markdown files are forced to be lowercase?!?** i dont really understand why they did it like this, liek its not even case insensitive

Example: to access `content/blog/testPost.md` you would need to type the url `https://clevertop.dev/blog/testpost` if you have the capital "P" then it *will not work!*

Anyhow, If you want to learn more about how the rest of the content system works (and tbh its pretty good apart from that one hiccup) then you can check it the documentation here: https://nuxt.com/docs/guide/directory-structure/content


## Inspriation 

Much of the sites style and code was inspired (and kinda copied) by bryley! Thankyou so much for showing my Nuxt and helping me learn it! Her site is here if you wanna check it out: https://brynblack.me/

As i develop my site more i hope to make its design more original but its been really nice to work with some existing code to learn the framework :3


## Todo List

- [ ] Properly make my own style/layout for the site
- [ ] Fix the way the pages are formatted differently between live and `npm run dev` (they look so much better int he preview T_T)
    - *its got something to do with `nuxt generate` vs `nuxt build` in the vercel setting i think, but on generate the site is blank sooooo, until i find a fix you shall have to see the weird formatting 😔*

--- 

Thats all i can think fo for now, if something else comes up i guess ill add it!

Heres my repo if you want see the code: https://github.com/Clevertop/vue-website

