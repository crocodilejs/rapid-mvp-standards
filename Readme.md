
# Rapid MVP Standards

> TLDR; This is a no-BS document defining rapid MVP standards.  It is based on my experiences, successes/failures over the past eight years in leading a rapid MVP startup/project/team, hyper-focused on apps.  This perspective of "success" and "failure" is purely based on ability to rapidly ship an MVP and test its viability - it is not based on any other factors, such as revenue.  Comments and pull requests are welcome.  Enjoy.

## Index

* [Background](#background)
* [Types of Standards](#types-of-standards)
* [Tool Standards](#tool-standards)
* [Development Standards](#development-standards)
* [Design Standards](#design-standards)
* [Project Management Standards](#project-management-standards)
* [Launch Standards](#launch-standards)
* [Testing Standards](#testing-standards)
* [Analysis Standards](#analysis-standards)
* [Growth Standards](#growth-standards)
* [Funding Standards](#funding-standards)
* [Random Standards](#random-standards)


## Background

The lifecycle of a project is typically short-lived, stressful, and uncertain.

This is due to various reasons related to internal (team/culture) and external (product/market-fit) problems.

Usually (from my experience), failure is a result of not focusing on what users want; not focusing on the core MVP product &ndash; and getting distracted along the way.

Failure is not due to a lack of funding.  Funding for a project is easily obtained (if team is stellar, product is solid, and product-market fit is spot on).

Failure is due to a lack of focus, dedication, and relentless shipping as fast as humanly possible (your health is definitely affected).

Failure is due to not thoroughly testing the project, the functionality, the core features.

Failure is due to giving up, to not staying committed, to not ensuring the team is dedicated.

Failure is due to not planning in advance, not thinking ahead, not expecting the unexpected.

The purpose of this document is to inspire, to serve as a guide &ndash; and to add whimsical enthusiasm for a successful project.

Its purpose is to help you define standards and to achieve greatness with your team while building apps in the quickest amount of time possible.


## Types of Standards

I have divided project standards into ten (10) categories:

* Tools - what tools and services are used to power communication, the app, and the team
* Development - ensuring the code is functional, tested, clean, to industry standards (relative to the programming language) and optimized for performance
* Design - ensuring the UI/UX is distinct, functional and fitting with the market and customer
* Project Management - interaction with clients, customers, and product team
* Launch - ensuring a successful launch and initial marketing push to validate the project
* Testing - ensuring tests are written properly, actually useful, and used
* Analysis - ensuring metrics and data is being analyzed and is then turned into useful and meaningful items
* Growth - ensuring the project is continously growing
* Funding - ensuring the project can stay alive
* Random - random bits of information to help ensure a positive project life cycle


## Tool Standards

* Gmail - for email ($5/user/mo - assuming 3 users = $15/mo)
* Google Calendar - for scheduling/meetings/reminders
* Digital Ocean or Linode - for servers (do not use AWS, it's a joke - other than CloudFront and S3, it is not useful for a scrappy/fast-paced startup) ($10/mo)
* Namecheap - for domain ($11/yr)
* RapidSSL - for SSL cert ($11/yr)
* AWS Route 53 - for DNS
* Slate - for API documentation
* Slack - for team chat and quick reminders using Slackbot (you can usually get $100 in free credit, which is more than enough time to get the project off the ground)
* Stripe - for payments
* GitHub - for code repository and issue tracking ($20/mo for organization)
* CircleCI - for continuous iteration
* Postmark (or Mandrill) - for transactional emails
* MailChimp - for blast newsletter emails
* Segment - for analytics tracking
* Google Analytics and Mixpanel (hooked into Segment) - for basic site metrics
* Dropbox - for file sharing (mainly design assets)

Total cost of essential tools per month: $45/mo<br />
Other yearly costs: $22<br />
Total estimated yearly costs: $562 ($45\*12 + $22)<br />


## Development Standards

* "RFA" - readme first approach - document in a Markdown file your plans for a project, include everything you can think of.  Spend at least 2 weeks on this.
* Code must be linted (while development is in progress, on file save, a linter must be run)
* All errors must be caught and handled, regardless of confidence in code
* Open source packages used must not allowed to be automatically upgraded
* Development environment must be minimal and fast - must use Mac or Ubuntu
* App must be tested on all of the latest devices/browsers/clients to market fit
* Developers must use vim (with as many plugins as possible) - no other IDE's should be allowed (a developer's finger muscle memory is critical to fast-paced coding &ndash; point-and-click is simply wrong and not optimal for productivity).  Atom may be used, however plugins are necessity.
* SSL encryption regardless if the service needs to be secure or not, encryption is important
* If the service includes anything financially related, use a Green EV SSL cert
* For code commits, use emoji prefixes, such as :book: for documentation, :bug: for bugs, :ledger: for renaming/moving/copying of files, :bulb: for features, and :lipstick: for code style fixes/refactoring
* Deployments should have zero downtime
* Deployments should occur with tagged versions (e.g. `v0.1.0`)
* Automated jobs should be managed with lock files or a system that spawns workers with specific deployment versions
* Regarding frameworks - I almost always suggest to go with the most minimal to start.  Don't worry about trying to invent the best framework; just use what works.  You can optimize and implement a new framework if the product really takes off.  Of course, don't pick something that is slow and painful to use.
* Deployments should have tagged versions with a `v` prefix and abide by semver versioning practices
* Are our assets minified, gzipped, concatenated, and served from CloudFront?
* Is the server locked down heavily? (e.g. all ports blocked except 80/443, fail2ban installed, auto-security updates, non-standard SSH port instead of 22 such as 44444, logwatch setup and emailed daily, etc)
* Does the server create backups of databases used for app storage?  Are they daily?
* Does the server allow root or password-based login attempts?  If so, disallow - SSH access only.
* Are other developers using an environment that closely mimics production and each other? (e.g. by using Vagrant/Docker or having the exact same workstations and package managers?)
* Are developers using git-extras and have common aliases for `git push`, `git commit`, and `git add .`?
* Are all outbound emails, sent by both @company.com Gmail/Postmark/Mandrill DKIM/SPF signed and DMARC compliant?  We need emails to land in users inboxes.
* Is our API designed properly with versioning, error handling, proper response codes, ease of integration, secure, and is documented?  Is the documentation up to date?
* Are we monitoring our server uptime and downtime?  What parts of our application are the slowest to respond?  What parts of our application take up the most CPU usage?  Investigate why and optimize.  Things need to be lightning fast, everywhere, always.  Speed wins.


## Design Standards

* Do not create mockups (in other words don't waste time conversing with developers or the client about how something should look, tell them how it is going to look) - designers should be experts and know exactly what to design without needing a mockup.  Based off R&D and market research, they, as designers, have the responsibility for this vision.
* Designs must be responsive and created with Sketch
* Designs must be exported with retina support (e.g. @1.5x, @2x, @3x versions)
* Designs must be synced to development team via Dropbox, all changes need to be published and a changelog must be sent to developers upon changes
* Developers must have experience with Sketch, in case the need of a quick export or to check the rgba/hex values during integration of a design.
* Are our assets exported and progressively optimized (and any other optimal reduction of file size taken place)?


## Project Management Standards

* Have we defined our team's mission with our team itself - and has everyone come to an agreement and signed the mission with their dedication to it?  Is the client in on this mission too?
* Is our team reminded of its mission weekly?  Do our team members have a form of communication to the PM as to what their thoughts are towards this mission?
* Are we constantly asking what do people dislike most about XYZ?  If not, we will never show them we listen to their concerns.
* Are we using common sense in our communications and interactions with the team and customer/client?
* Are we keeping in check with existing commitments made by team members, by the client, by ourself?
* Is any work (e.g. a product feature) being worked on a complete waste of time and will not contribute to a positive end result?
* Are we continously reviewing offers and satisfaction levels based off requests and communictions made?
* What is the team's current mood?  What has their mood been in the past?  How has it related to productivity and growth, success, etc?
* What is the customer or client's mood?  How has their mood related to their purchases, or use of the app?  How has their mood related to their communication level?  When they are distant - does that mean they are unhappy?  Communication issues are extremely common.
* Are we constantly showing continous progress?  If not, or if we don't think we can - think of visuals or other meaningful ways to show progress (e.g. screenshots, a quick video narrating what you're working on - even if its showing code, or a feature work in progress, etc)
* Keep the burn rate low - do not use or pay for services you don't use - or don't need - or don't directly impact the project
* Weekly meetings with the client in-person/face-to-face using Google Hangouts
* Continuously send and respond to emails, as soon as you see them - even if it just to say "OK got it, expect a response soon"
* Are our developers and designers pushing work daily?  Are we seeing the work and not just hearing it has been done?  Seeing is believing.
* Customer and client satisfaction is the most impactful over all other standards
* Are all issues that developers and designers are working on in GitHub and well-documented?
* Is the client or customer aware at all times of any improvements, fixes, or changes being made to the app?
* Do we have milestones in GitHub with a timeline of issues to finish by a deadline?
* Are our labels in GitHub fun, meaningful, and relevant?
* Is everything quickly readable?
* Are issues being referenced to one another when appropriate?
* Does a team member always have a plate of at least 2-3 items assigned to them in GitHub at a time?
* Does the project manager frequently comment on issues, even if it's just to say "good job?" or "I think the pixels are in this are wrong, please talk to designer", or "The code here needs refactored, its a mess"
* Is the communication in the Slack room with the client (or is our communication with our customer over email too confusing or wordy?).  If so, it gives the impression we are unorganized, not succinct, and don't know how to get our point across in an analagous way.  Cut out as many words as possible when communicating with the client or customer - we want to seem as confident, focused, and clear as possible.  Are we actually answering their questions?
* Are we charging what we're worth?  Are we paying ourselves what we deserve and need?
* How satisfied is the client/customer? (e.g. Net Promoter score - survey - weekly/monthly)


## Launch Standards

* Did we have a mailing list or splash page in advance?  Is our message ready for them?  Does our message make sense?
* What press will we contact?
* Who or what marketing effort will we leverage to give the project the initial push it needs - to acquire users in order to validate the product is a good market-fit?
* Are we even ready to launch?  Does the product even make sense to people that haven't seen it before?
* When we explain our product to someone else, or show them a demo - do they simply say "cool" or "OK"?  Or are they asking lots of questions - if they are, it means we're doing something right, so listen to them.  What were their questions and how can we answer it ahead of time for everyone else like them?
* How will our initial launch convert people to users?  Will we blast out 1000 emails and get no users?  If we can envision this occuring, what can we change that will fix this?
* Is our explanation of the product too complicated?  Do we compare ourselves to competitors as to why we're better?  Or what features we have that they don't have?  Or what new offerings we bring that are value-adds for users?


## Testing Standards

* Does our production server get tested before deployment finishes?
* Are tests even being written?
* Are we actively deploying our test cases to production or keeping them in development branch only?
* Are tests above 50%?  If so, how could we get them to 75%?  If they are at 75%, what is preventing them from being 100%?
* Are we using the best testing tools available?


## Analysis Standards

* Do we have a fun dashboard to look at with metrics?
* Do we have a bot automated to make a "ding" noise whenever a new customer or user signs up?  Do we get a "ding" when our client/customer says we're doing a good job?  Do we get a "ding" when we're not doing good?  How do we reflect, reward, or scold ourselves when this "ding" happens?
* How frequently are the lead developers and designers reviewing code, pull requests, merges, and changelogs?
* How frequently are the lead designers inspecting what developers implement to ensure quality and envisioned interaction is achieved?
* Are all clicks from emails user-trackable with Events?
* Are we looking at our funnel, and saying, OK here is the start event, here is the end event for our conversion to be "successful" - now what are the common steps in between (e.g. what is the path a user takes from Visiting a site to Checking out - and how can we simplify it more - or what road blocks are users running into)?
* Is our funnel optimized?
* How are our A/B tests performing?
* Are we running at least 5 experiments/tests a week?


## Growth Standards

* How is our search engine optimization?  Are all pages recorded in a sitemap?  Is it submitted to Google?  Do all pages have Schema.org schemas (e.g. Product, Recipe, Event)? Are page titles and descriptions simple and relevant? (max 55 characters for title and 115 for description)
* Are we blogging for long-term growth and to create meaningful value with our market, besides what product/service that our app offers?  Using a service like Amazon Mechanical Turk or Fiverr to write unique relevant content with keywords?
* Are we experimenting enough?  Do our experiments make sense and have we thought them through?
* Are we paying attention to user retention?  Are we targeting segments of customers that have been inactive to figure out why?  Are we asking or reviewing what the power-users are doing on the app and how to make that experience easier?  Power-users are a very special and meaningful user segment, possibly the most meaningful - they will most likely pay the most.  Are we automating our messages to users with a service like Intercom - and not coming across like spammers?
* Are we doing research as to what strategies have worked for other similar companies to attract users?


## Funding Standards

* Always, always bill upon time, not upon scope of work.
* If you're looking for funding - the only reason should be to accelerate your growth.  It should not just be to have money for some project.
* If it is for any other reason, such as a lack of funds to pay existing employees, then your burn rate is too high and you aren't being scrappy enough.  If you have to hire developers or designers, could you not learn to code yourself?  If so, would you be wasting your time you could spend working with customers?  It's a delicate balance, with an end result, or cyclical result involving lots of risk and little potential of reward.
* Are you going to the right investors?  Will they help you besides just giving you a bucket of money to put in your bank account?
* Usually you can bootstrap the project entirely, but only if you are smart enough.  The topic of bootstrapped/lifestyle vs. VC funding can be handled in another medium.
* Can we get 3 clients to pay $K up-front that will support us?  Can we reward them for this if things work out?  Do they get a refund if it doesn't?
* How can we sell vaporware and deliver quickly?


## Random Standards

* Are our developers, designer, and project manager constantly making time for improvement?  Are they thinking of how to help each other?  Are they spending time learning on their own?  Are developers contributing to open source or writing blog articles about technical concepts that they solved or did research and have findings to share upon?  Are designers publishing their work and drawing inspiration from others?
* VPN's are not needed - they slow things down and cause issues with deployment - developers should be the ones using VPN's and a secure network, not the server.  You're only as fast as your slowest link.
* Are we having fun?  If not, then how can we make this project fun?  Can we add whimsys somehow?  Can we make the brand emotionally attractive to us and our customers at the same time?
* DevOps teams are not needed and slow things down - most of the time developers can do things themselves, or if something critical were to happen - developers should be full-stack experts and know how to fix it themselves.  Developers are savvy, scrappy folks that like to do things quick.  They read and implement best practices in the industry - they are the ones that know their stack the best and know how to implement and iterate the fastest - to satisfy customers and clients - anything that gets in their way is a roadblock and should be demolished.
* Does our team make sense?  Is everyone up to par on our standards?  Are we constantly having to code review and make the same code comments?  Are developers not making use of linters or writing tests when appropriate?  Are developers not simply thinking of the app as a whole while writing a feature - thus in term affecting 10x other things negatively?
* If a developer sees something wrong - do they let it go by, lazily, or do they actually take the time and care to implement a fix, even if it's just a :lipstick: code cleanup or DRY refactoring, or deleting of code that is no longer used?
