---
title: devops-beszel-community
tags: [beszel, community, devops]
created: 2026-08-28T17:49:17.598Z
modified: 2026-08-28T17:49:28.965Z
---

# devops-beszel-community

# guide

# discuss-stars
- ## 

- ## 

- ## 

- ## 

- ## 
# discuss-news/changelog
- ## 

- ## 

- ## 

- ## 

- ## 
# discuss-issues
- ## 

- ## 

- ## 

- ## 

- ## 
# discuss-tips
- ## 

- ## 

- ## 

- ## 

- ## 
# discuss
- ## 

- ## 

- ## 

- ## 

- ## [Didn't know it so easy to setup and looks really good with Beszel. : r/homelab _202603](https://www.reddit.com/r/homelab/comments/1s6xl6m/didnt_know_it_so_easy_to_setup_and_looks_really/)
- Loved beszel for a while, but now I am starting to transition my homelab setup to dockhand to reduce overhead of monitoring tools. Beszel is solid for sure though.
  - What overhead? My Beszel Hub LXC peaks at 0.2% of a single N95 core and uses 35mb of RAM. The docker container for the agent uses even less CPU, and currently shows 12mb RAM.
- True that Beszel doesn't use a ton of room, it was one among many different management and monitoring tools I had running (grafana, beszel, dashdot, dockge, portainer). I am trying to eliminate all of them to get rid of additional redundancy and overhead around my network overall. Dockhand seems to be the all-in-one I need at the moment for my homelab
- i have no idea what are you talking lol. Dockhand use much more resource compare to Beszel. My switch decision just based on thinking that i only need monitor stuffs, not trying to manage docker or anything or so

- I was using Pulse, but that was a terrible and buggy experience. I moved to Beszel right after. It's still missing zfs support, but I see chatter about it on the issue tracker. Hopefully that will come sooner than later.

- Is there a way to monitor URLs with Beszel similar to uptime-kuma?
  - I dont think you can. Its not the same purpose

- ## [Beszel vs. Pulse : r/selfhosted _202601](https://www.reddit.com/r/selfhosted/comments/1qqkx48/beszel_vs_pulse/)
- In my case pulse has a high cpu cost that beszel don’t have
  - Its in agent side or server side? I use beszel for now, and will try pulse

- pulse I found easier to copy paste and deploy.

has notifications if you like that kinda thing too

- ## [Glances or Beszel, which one is lighter? : r/selfhosted _202502](https://www.reddit.com/r/selfhosted/comments/1iw4xxq/glances_or_beszel_which_one_is_lighter/)
- I run both, and Glances is a much more resource-hungry service.
  - I've run both as well and can confirm this. Beszel uses basically no resources while Glances eats CPU, just to show a fancy and not very useful htop interface.
