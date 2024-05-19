---
layout: post
title:  "Three Products of Robotics"
comments: true
date:   2022-11-27
---

One of the great potentials of Artificial General Intelligence is advanced robotics. Machines that can manipulate matter in physical space aligned to the interests and needs of their creators. According to Wikipedia, <a href="https://en.wikipedia.org/wiki/History_of_artificial_intelligence#Mythical,_fictional,_and_speculative_precursors">one of the first myths</a> about AI was a giant bronze statue called <a href="https://en.wikipedia.org/wiki/Talos">Talos</a> that would patrol the island of Crete three times a day. Humanity has long sought artificial intelligence for the benefits of manipulating matter and perfoming rote tasks. 

However, despite marvelous <a href="https://www.forbes.com/sites/forbesbusinesscouncil/2022/10/07/recent-advancements-in-artificial-intelligence/">recent advancements in AI applications</a>, robotics still feels very far off. I for one thought the future would have an order of magnitude more robots. But that is not where things are headed. In July 2021, <a href="https://openai.com">OpenAI</a> announced that they were <a href="https://www.therobotreport.com/openai-abandons-robotics-research/">stopping robotics research</a>. One of the reasons cited was lack of data. Wojciech Zaremba (Co-founder of OpenAI) said: <em>"So it turns out that we can make a gigantic progress whenever we have access to data. And I kept all of our machinery unsupervised, [using] reinforcement learning — [it] work[s] extremely well. There [are] actually plenty of domains that are very, very rich with data. And ultimately that was holding us back in terms of robotics"</em> (per a <a href="https://venturebeat.com/business/openai-disbands-its-robotics-research-team/">VenureBeat article</a>). Meanwhile projects like <a href="https://github.com/openai/robogym">Robogym</a> and <a href="https://github.com/SerpentAI/SerpentAI">Serpent AI</a> have not seen commits in 2 years (as of this writing). 

Wojciech Zaremba's claim that <em>low data availability</em> has hindered progress with robotics, aligns with how <a href="">reinforcement learning</a> algorithms work in general. Algorithms like <a href="">Proximal Policy Optimization (PPO)</a> use iterations to approximate the best decision or "policy" for the agent to make. While reinforcement learning's general abstractions of rewards, policies, agents, and environments may be the right path forward -- it seems that we need better policies that are more efficient at learning through data rather than compute. For example, PPO could theoretically learn the best way to drive a car given enough compute time. Take a real world car, a PPO agent, and 1MM years of experience and you'd have a passable agent. But that approach is not viable. Intelligence is more than brute force search.

Below are <b>Three Products of Robotics</b> that would make (at least my life) more enjoyable and free up more time. I'm writing them out as a way to focus data collection, think about the surrounding systems, define what a policy engine would use as inputs/outputs, the reward functions, and the feedback loops. I may in the future write more about each of these. I also briefly mention a few "runners up" that would be helpful. One caveat is that it seems entirely plausable that each of these three products could be solved in a generalizable way in terms of the policy models, the feedback systems, the reward calculations, and even the physical devices.

<ol>
<li>
<h2>Laundry Bot</h2>
<p><em>Description:</em> the goal of this robot would be to take a pile of used clothing (underwear, dry-clean-only, pants, socks, belts, and other non-laundry foreign objects like toys) as input and then output clean, folded, and hung clothing on hangers. The system would allow preferences for things such as T-Shirts that should be hung up on hangers and ones that should be folded. Ideally, this feedback could be per garment. My 3 Fit Theory T-Shirts go on hangers, but the old Mossimo ones get folded. I can put everything away in the closet. The systems purpose is to sort, wash, dry, and fold. 
</p>
<p><em>Rewards & Feedback:</em> Laundry Bot could use 

</li>

<li><b>Dish Bot</b> - the goal of this robot would be to take used dishes (utensils, plates, mugs, and other non-dish foreign objects like a book, food. 

</li>

<li><b>Tidy Bot</b> - the goal of this robot would be to put objects away. Take

</li>

</ol>

