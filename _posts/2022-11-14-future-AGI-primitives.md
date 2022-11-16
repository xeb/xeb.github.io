---
layout: post
title:  "Future AGI Primitives"
comments: true
date:   2022-11-14
---

I know AGI predictions are rote but I’m going to write some down anyways. After all, intelligence is in many ways the act of prediction, right? Shouldn’t the field of artificial intelligence have an expectation — nay an obligation! — to continually refine predictions of its own future outcomes and capabilities?

Actually, let’s make this list more of my own wishlist for AI and AI-adjacent technologies (which may or may not be viable businesses). These seem important in the coming intelligence explosion we find ourselves in.

<ol class="alist">

<li><span id="Emissary" class="em">Emissary</span> - Imagine a system that acts as an authorized and cryptographically signed emissary for a known human being. The agent is sent off to perform actions. Those actions are the legal responsibility of the human owner (unless fault can be found with other systems). The Emissary is the primary, customized, and individual personality of an AGI for each human to interact with.

<div class="example center">
<a href="https://www.amazon.com/Agency-William-Gibson/dp/110198693X">
<img src="https://m.media-amazon.com/images/I/41vnz9typ+L._SY344_BO1,204,203,200_.jpg" width="20%"/>
</a>
<i><span class="ems">Eunice -- from <a href="https://www.amazon.com/Agency-William-Gibson/dp/110198693X">William Gibson's book Agency</a> -- is an example of an Emissary (but albeit "unbound" to a human)</span></i>
</div>

</li>

<li><span id="AIUI" class="em">AI-UIs</span> - Imagine interactions with future AGIs to be based on dynamic visual user interfaces. UIs that are personalized, dynamic, and contextual. While <a href="https://twitter.com/sama/status/1515766238751834114">language interfaces</a> are quickly becoming pervasive (or at least folks talk about them being all the rage!). Typing or transcribing text tokens just takes <i>longer</i> compared to a single "<b>CONFIRM</b>" button. <br/><br/>

Example: a system needs to prompt a user to pick a new appointment date. Rather than a classic date picker, an AI-powered UI model generates (given different contexts and calendar data) three buttons: 
<div class="example center">
<button>First Thing Monday Morning <span class="subtitle">[Before Kid Drop-Off at 7am]<br/>
<span class="preference">(your likely preference)</span></span></button><br/>
<button>Lunch on Tuesday<span class="subtitle">[Next Wednesday after your 11:30am with Ian]</span></button><br/>
<button>Friday Evening <span class="subtitle">[Kids have Soccer that Night]</span></button>
</div>
</li>

<li><span id="DataSteward" class="em">Data Stewards</span> - Imagine an AI-powered authorization system that is trained over-time on your data access requests. Any time an <a href="#AIUI" class="ems">AIUI</a> or foreign system needs access to your: calendar, email, contacts, photos, memories, or physical access to your home -- a <a class="ems" href="#DataSteward">Data Steward</a> system can infer the human or agent's intent and authorization status. When in doubt, the Data Steward can leverage an <span class="ems">AIUI</span> to confirm access.

<!-- example permission -->
<br/><br/>
<b class="ems">Alex-to-Emissary:</b> "ask Mark to send me the pictures of our families at the beach"<br/><br/>

<i>(Alex's <a href="#Emissary" class="ems">Emissary</a> reaches out to my <a href="#DataSteward" class="ems">Data Steward</a>)</i><br/>
<i>(My <a href="#DataSteward" class="ems">Data Steward</a> thinks this is fairly normal, but given the context of me in a bathing suit, thinks it is best to ask permission first from me and then send a note to Alex's <a href="#Emissary" class="ems">Emissary</a>)</i><br/>
<i>(My <a href="#DataSteward" class="ems">Data Steward</a> leverages an <a href="#AIUI" class="ems">AIUI</a> to ask me one simple question:)</i><br/>
<br/>
<b class="ems">Data Steward-to-Mark:</b> "Do you want to share your Beach pictures from Saturday at Doheny Beach with Alex Jones?"<br/>

<div class="example center">
<button class="yes">Yes <span class="subtitle">[You have shared 10k pictures with Alex in the past from this location]</span></button><br/>
<button class="no">No <span class="subtitle">[You'd like to review them all later]</span></button><br/>
</div>

</li>


<!-- Media Types -->
<li><span class="em">Inferential Media Types</span> - Our data needs to be progressively augmented with intelligent inferences. JPEG <a href="https://en.wikipedia.org/wiki/Exif">EXIF</a> data should have binary embeddings or hashes of FaceNet IDs that the custodians of the image are able to parse out. Computer vision models need to augment the raw media files they process to progressively enhance them rather than keeping that knowledge separate. 
<!-- Model Experience -->
<li><span class="em">Model Development Experience</span> — Composing and using models in Python is not as accessible as JavaScript and web app development was 20 years ago. We need more. If <a href="http://theinsideview.ai/ethan">Scale is All You Need</a>, then AI Infrastructure needs a ton of work! The big ones on my list are: apt-sourced NVIDIA drivers (including CUDA and cuDNN) that works out of the box, standards for model storage (should all models be versioned in docker so inference and future training contains the right dependencies of the algorithm?). We also need composable models. I want to chain computer vision pipelines together, then add automated speech recognition later.
</li>
<!-- AOSes -->
<li><span class="em">Assistive Operating Systems</span> - <a href="https://www.adept.ai/act">Adept and ACT-1</a> are awesome looking! how can I get my entire Operating System to be assistive by AI in a generalized way? Automatically suggesting completions for me or text? Maybe we need a "accept suggestion" key on a keyboard.

<!-- Burst Computer -->
<li><span class="em">Burst Compute</span> - massive infrastructure for extremely brief periods of time. I want 1,000x A100s for 15 seconds and not pay a penny more. My <a href="#Emissary" class="ems">Emissary</a> and personalized <a href="#DataSteward" class="ems">Data Steward</a> will authorize any devices, agents, or other intelligences in my digital and physical life with necessary burst compute. It's not feasible to build a smart switch with the latest ASR and NLU/NLP models to carry on a conversation, but it is reasonable to put the instruments (microphone and speaker) with cloud access to get the compute to carry on a conversation as needed during setup. I imagine we'd also want the <a href="#DataSteward" class="ems">Data Steward</a> authorizing the compute to be swappable. If my Dad is chatting away at my smart switch -- he should pay for that GPU time. Get your own personified plug, Dad!
</li>

<!-- Embedded Agents -->
<li><span class="em">Embedded Agents</span> - Smart Home device setup sucks. Can I get 10 different brands under the same roof and get them to get along? Will my <a href="#Emissary">Emissary</a> and <a href="#DataSteward">Data Steward</a> be the primary ones responsibly for keeping these devices in check? And if they do not -- how can I interrogate them? <br/><br/>

<!-- example wifi connect -->
<b class="ems">Mark-to-Emissary:</b> "do you see this smart switch? What is it? It won't turn on."<br/><br/>

<i>(Mark's <a href="#Emissary" class="ems">Emissary</a> reaches out to the <a href="#DataSteward" class="ems">Data Steward</a> in the device -- there is no Emissary becuase the device, in this case, was not sent by a human)</i><br/>
<i>(The smart switch <a href="#DataSteward" class="ems">Data Steward</a> says it has no WiFi password saved. It used to belong to a similar SSID but the old password doesn't match. The <a href="#Emissary" class="ems">Emissary</a> recognizes the MAC address and the old WPA/2 authentication keyphrase. This is indeed an old switch. The Emissary asks if the switch can have the latest WiFi)</i><br/>
<br/>
<b class="ems">Data Steward-to-Mark:</b> "This is an old Smart Switch that was disabled 2 years ago. Do you want me to share your latest network configuration with it and install it into the alarm system sensor array?"<br/>

<div class="example center">
<button class="yes">Confirm <span class="subtitle">[Smart Switch will be named "Christmas Tree", you can change it later]</span></button><br/>
<button class="">No, not today <span class="subtitle">[You want more time]</span></button><br/>
</div>

</li>
<li><span class="em">Verifiable Robotics</span> — This is the penultimate for me. An action transformer turned into the physical universe. Truly multi-modal. Simulation can be like unit tests, but we need a primitive for integration tests. Huge warehouses where robots can be tested offsite and virutally. Perhaps they have simulated models of my home (that do not physically exist), but the robots themselves are real and have to "take a spin around the house" ensuring they work with other agents and systems deployed. 
<img src="/img/DALL·E 2022-11-14 23.17.05 - a classroom full of robots each learning how to walk, with a human instructor cheering them on, photograph, ultra-realistic, 35mm, DSLR, TIME photogra.png" />
</li>
