---
layout: post
title:  "Lessons Learned from a 20-year-old Web App"
comments: true
date:   2022-05-19
---

<p>After I read "<a href=
"https://www.getlago.com/blog/why-billing-systems-are-a-nightmare-for-engineers"
target="_blank">Why billing systems are a nightmare for
engineers</a>", I thought it would be fun to write about my own
experience. Specifically lessons I've learned from building and
supporting a 20 year old (and counting) "ERP" web app. But first,
let me explain a bit how this came to be.<br></p>
The web app is a general ledger, project management, inventory
management, HR, and general "<a href=
"https://en.wikipedia.org/wiki/Enterprise_resource_planning"
target="_blank">ERP</a>" system (including billing, invoicing,
foreign currency purchases, etc.) for 20-30 users at a small
interior finishing supplies company which my grandfather founded.
It has been used every day for at least 20 years.
<p><u><b>Building iteratively for years</b></u><br></p>
<p>My Dad decided to give me a chance at building software for the
family business before I was out of high school. I had shown an
aptitude for programming and was making good money with friends
building local websites. He built a COBOL system for the family
business when he was my age, so the legacy was passed on to me
(which I am very grateful for). My Dad made it a bit easier for me
and bought a GUI code generator that would create CRUD pages in PHP
using a MySQL backend. The LAMP (Linux Apache PHP and MySQL) stack
was all the rage back then. My Dad's role was to design the
relational database schema while I made pages (mixed PHP and HTML)
to create, update, and delete entities from the database.</p>
<p>We started small with a simple project management app. We
trialed it with a few users in the company, got feedback, and kept
going. One summer I setup a door desk in the office. Literally a
door on top of two filing cabinets. Unlike the <a href=
"https://www.aboutamazon.com/news/workplace/how-to-build-your-own-amazon-door-desk"
target="_blank">Amazon story</a>, I did not have braces or legs,
just filing cabinets. I had an old Toshiba laptop and spend
hundreds of hours for at least 2 months build the core of the
application.</p>
<p>Our goal that summer was to replace all the paid software at the
company, apart from operating systems, and Microsoft Office. It was
cheaper to pay me by the hour, after all, than ongoing license
costs for the alternative ERP systems everyone hated. By February
2003, we had fully transitioned to our own makeshift LAMP stack
with 7 sub-systems. While I still run some occasional maintenance,
the system has been stable for years requiring no oversight. I feel
lucky for the chance to build it, but remain constantly paranoid
about it's up-time, security, and potential for catastrophic
failure.<br></p>
<p><u><b>App Stats:</b></u><br></p>
<p>- 2 developers (me & my Dad)</p>
<p>- Running on a single m3.xlarge instance in AWS (with a
failover), after it ran on-prem for a decade<br></p>
<p>- 19GB used on disk (code, DB, and jobs)</p>
<p>- 15 cron jobs<br></p>
<p>-&nbsp; 2,543 PHP files<br></p>
<p>- 3.5 million lines of PHP (<span style=
"font-family: courier;">find . -name '*.php' -print0 | wc -w
--files0-from=-</span>)<br></p>
<p>- 1.9GB MySQL storage (<span style="font-family: courier;">du
-sh /var/lib/mysql</span>)</p>
<p>- 9 MySQL DBs, largest table has 1.5M rows - not that
big!<br></p>
<p>- 23 active users this week (<span style=
"font-family: courier;">cat access_log* | grep "/login*" | awk
'{print $1}' | sort | uniq | wc -l</span>)<br></p>
<p><br></p>
<p><u><b>Lessons Learned</b></u></p>
<p><b>- <a href=
"https://www.dreamsongs.com/WorseIsBetter.html">Worse is
better</a>.</b> The app feels like a giant hack and always has. But
its beautiful in its own insane way. It grew as needed and that was
better than something built really well launched in big version
releases. I cut my teeth on it and am grateful to the poor users
who were forced to put up with my bugs -- I know now how much of a
privilege that was.<br></p>
<p><b>- No libraries, just global functions.</b> This is bad
advice, but it's served me well as a lone developer over the years.
I have a single <span style=
"font-family: courier;">globals.php</span> script that every
application in the system uses, and for the main sub-system (called
"Distribution Master") I have a single <span style=
"font-family: courier;">functions.php</span> script. Only the
navigation elements are shared.<br></p>
<p><b>- Create single purpose features.</b> Whenever a new feature
was requested, I would create a new PHP script. A few pages -- like
the Invoicing routine -- I would version & keep multiple copies
around. This makes finding anything in the system very easy.
Whenever something would break & I would ask the user to report it
-- they could give me a URL and I'd instantly know which file to go
and fix.<br></p>
<p><b>- Use cron and stop worrying.</b> It took me a few years to
realize this, but time-based automation is easy to grok, easy to
debug, and easy to explain to others. More complex triggering
automation based on events sounds better, but <span style=
"font-family: courier;">crontab -l</span> is a godsend when I've
forgotten how everything works in the background system routines. I
don't even bother with daemons anymore.<br></p>
<p><b>- Test in production.</b> Heck I've edited code live on the
production server a few times. The production deployment is tied to
our Git repo so I can pull and push from our main branch. I know,
it's insane and kind of stupid! But I didn't have time to properly
test in another environment and then deploy. Since it's just been
me -- I know how to manage risks of breaking something, undoing it.
Plus having single-purpose-pages means I can create a copy of a
script, test it in prod, and relink when it's working.</p>
<p><br></p>
<p><u><b>Final Thoughts<br></b></u></p>
<p>The system never became the foundation of a startup (which we
dreamed of at one point). We may have missed an opportunity.
However, it was the bread & butter of a business that put food on
the table for dozens of people for decades. If you want to fast, go
alone; if you want to go far, go together. The system won't make it
another 20 years, but it surprises me how simple, "hacky",
not-following-the-trends gave me opportunity and worked so well for
years.<br></p>
