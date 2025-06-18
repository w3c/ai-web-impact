# The Agentic Web: risks and opportunities

# Abstract

This document proposes an analysis of the potential impact of the deployment of AI agents on the Web, the role that web standardization may play in managing that impact, and how to provide users of these tools with mission-aligned guardrails.

# Status of this document

This document has no standing and is in active development to support structured conversations on the topic within the W3C community, possibly leading to a dedicated W3C Workshop.

# Terminology

The taxonomy of what constitutes an AI Agent is still in active flux; for the purpose of this document, we define an AI Agent as a piece of software making use of AI technologies (typically LLMs and other Machine Learning models) to interact autonomously or semi-autonomously with disparate content and services to accomplish complex tasks. These agents can act directly on behalf of an end user, or when prompted by other agents or external circumstances.

# Scope

This document complements the existing [AI & the Web: Understanding and managing the impact of Machine Learning models on the Web](https://www.w3.org/reports/ai-web-impact/) report which looks at the impact on the Web of AI systems and Machine Learning models more generally. That report covers a number of systemic impacts of these systems while the current document focuses specifically on what AI Agents change to that picture. In particular, this document does not include considerations associated with how the Web is impacted by ML model training since AI Agents are built downstream from such an activity which is covered in the broader report.

# AI Agents Interacting with the Web

The Web is arguably the primary platform to expose digital content and services and thus constitutes an unavoidable source and target for AI Agents.  
We posit that the impact of AI Agents will differ vastly depending on the nature of Web end points: in particular, we describe below how the impact may differ for *content* compared to *online services*.

## Impact on Web Content

AI Agents are likely to have a significant impact on common Web business models. 

Many Web sites rely on users directly perceiving content for monetization (e.g. via advertising). At the same time, many sites rely on analytics in order to tailor content to users, gather insights for new content, and justify the expense of producing the content. 

AI Agents are likely to have an impact on both monetization and analytics, but the impact is likely to vary based on two main usage scenarios:

* Targeted consumption (e.g., watching a movie, listening to music),  
* Information gathering (e.g., picking a vacation destination). 

For the latter user experiences, so-called "deep research" AI agents have already appeared on the scene. Some operate on traditional search sites, but others move search capabilities directly into the browser and may replace some types of traditional search engine web sites. In doing so, these AI Agents directly impact monetization opportunities for those sites, which may jeopardize their livelihood. Early signals of reduced visits from search engines suggest this is already occurring. Unless alternatives are established to mitigate this impact, a significant portion of content producers may no longer be able to distribute their content openly, reducing the overall value of the Web both for end users and AI Agents.

Such alternatives likely include:

* Monetization of information gathering by AI Agents through **micro-transactions** (micropayments, or possibly novel ways of re-using advertising in an agent-mediated operation);  
* New **analytics end-points** where AI Agents autonomously report what information they've made use of possibly with some context in a privacy-sensitive way.

Either of those would require significant changes in the ecosystem and entail setting up complex interoperable interfaces to make them possible at all.

Conversely, while micropayments have long been considered as an alternative to advertising (with some of its undesirable externalities e.g. on privacy), they haven't so far managed to emerge as a credible ecosystem of comparable scale \- AI Agents may offer a novel path to such a scale, as they combine an environment that end users have been trained to pay for (and arguably, through a model of micro-payment itself with their per-token pricing), with systems that can alleviate a lot of the friction typically associated with micropayments. One could imagine for instance that, upon being presented with a deep research request, an AI Agent would calculate the total cost of such a request inclusive of micropayments to sources being consulted.

In such an ecosystem, or already today for content providers with no or limited dependency on monetization or analytics, another need is emerging to make AI Agents more effective in their tasks: customizing how content is delivered or made discoverable to them ([llms.txt](https://llmstxt.org/), exposure of data and APIs through MCP). 

Similar situations have arisen at different points of the Web history: the development of content tailored specifically for people with disabilities, or for search engines, or for mobile devices. While there are indeed situations where these alternative views are justified or even required, the value of maintaining the [one Web principle](https://www.w3.org/TR/ethical-web-principles/#oneweb) points towards a path facilitating convergence with existing discovery and rendering mechanisms rather than ones that strengthen separate windows on the Web. In particular, it seems likely in this case as in previous ones that a semantic-rich progressive-enhancement based approach to developing content would provide a strong basis to serve the needs from AI Agents.

Risks:

* Depletion of openly distributed Web content  
* New intermediation between content producers and their users creates a disconnect in the feedback loop  and reduce brand recognition for content creators
* Two-tier Web experiences for users with or without agents

Opportunities:

* Diversify monetization models for content producers through new momentum behind micro-transactions

## Impact on Online Services

In our model, Web Content is an end in itself, while we think of a Web Service as a means to an end. A shopping portal enables users to make purchases, a government portal enables users to perform civic duties, and so on. People using these services often "just want to get something done" and the more friction they encounter, the less they appreciate the service. This suggests a significant opportunity for AI Agents: reduce service friction.

This would offer multiple potential benefits:

* lower costs (for example, by lowering transaction abandonment or increasing competition across providers)  
* enriched services (for example, by simplifying otherwise overly complex tasks, and thus engaging users is new ways)  
* increased productivity (if users need to spend less time to achieve a given complex task)

In many cases, AI Agents will reduce friction by carrying out actions autonomously on behalf of the user. Building this future will involve some critical standardized building blocks.

An emerging architecture for optimizing services delivery to AI Agents is via dedicated formats and protocols: either where these services are considered as traditional non-AI end points ("tools" as it would be described e.g. in MCP), or where these services themselves are exposed as AI Agents. There are a lot of active developments in establishing such protocols, most of them currently happen outside of traditional standards organizations.

Any complex workflow involving multiple agents will need a robust **identity framework** that can scale to agents operated in private and in public, controlled by organizations or individuals, most of them with limited cryptographic skills, yet possibly increased dependency on the actions they delegate to their agents.

This will most likely need improvements in **permission delegation**. How can an end user safely grant permission to an agent to represent them in a transaction that may entail combining authentication across multiple services? Compared to today's federated authentication approaches, we will likely need a way to describe much more fine-grained permissions, and ensure they are discoverable before a transaction. Engineers have begun thinking about this problem (e.g., in [The future of AI agents—and why OAuth must evolve](https://techcommunity.microsoft.com/blog/microsoft-entra-blog/the-future-of-ai-agents%E2%80%94and-why-oauth-must-evolve/3827391)).

AI Agents will themselves be working together, so another important brick involves **service orchestration**. Long ago W3C explored standardization in this area through the [Web Services stack](https://www.w3.org/TR/ws-arch). More recently and more relevant, W3C's evolving [Web of Things stack](https://www.w3.org/TR/wot-architecture11/) can be used in this environment of agent to agent communication, as illustrated by the [Eclipse LMOS protocol](https://eclipse.dev/lmos/docs/lmos_protocol/introduction/).   
There has been at least one significant change in circumstances since these stacks were originally developed: LLMs are now able to translate concepts across formats and languages. Even in this new world, we can learn lessons from previous efforts, such as analyzing why Web Services, though strongly supported by key industry players, failed to have their anticipated impact.

Risks:

* 

Opportunities:

* 

# AI Agents as Web User Agents

Authentication managers, smart autocomplete, payments, and malware protection all illustrate how browser automation or semi-automation can make end users' lives on the Web  easier. In some cases, these capabilities blur the line between the browser and Web content. For example, in most browsers the URL bar is no longer just for URLs: users can type queries that are then fed to a search engine running on a Web site. This convenient UX leads many users to think that the user agent is performing the search, even though a Web site did so.

As mentioned above, AI Agents may replace the typical search-and-browse approach, further blurring the browser/web content distinction when it comes to search. New automation enhancements such as enabling users to issue natural language commands to the browser or web site, and enacting complex workflows across pages and sites (incl. form filling and submission) will further blur the line, and more importantly, raise fundamental questions of trust.

For example, LLM-based systems suffer from so-called "hallucinations" that may lead AI Agents to take nonsensical or harmful actions; depending on the sensitivity activity they would be automating, these hallucinations could create significant harm to the end users they're supposed to represent, with significant detrimental impact on the trust end users would have in agents, but also possibly in online systems in general.

The inability to establish a robust boundary between prompts and other input in LLM-based systems has already allowed prompt-injection attacks in many contexts. In an environment as open as the Web, and from a context as sensitive as the one managed today by browsers, such attacks could cause serious harm to users (see also [AI in the Browser Threat Modeling](https://github.com/w3c-cg/threat-modeling/blob/simoneonofri-patch-2/models/ai-in-browser.md)).

A longstanding principle of Web architecture has been that the browser represents the user's interests. As the [W3C Technical Architecture Group (TAG) writes](https://w3ctag.github.io/user-agents/), "A user agent acts as an intermediary between a person (its user) and the web... The user agent serves the person as a trustworthy agent: it always puts that person's interest first." As AI Agents transform the browser landscape, how will they earn our trust?

Browsers have (to a large extent) earned user trust by performing "duties" on behalf of the user. Beyond any moral or legal considerations, these duties have played a critical role in enabling a flourishing ecosystem for both end users and content providers. The extent to which these duties can be applied in the less controlled environment induced by LLM-powered systems remains to be seen. For instance, browsers take pains to not expose the sites a user has already visited. Are there risks that an AI-based system would risk surfacing not only browsing history but maybe even prompt history?

Generally speaking, the current user experience of web browsers tells a relatively clear liability story: when something goes wrong we can tell whether there was user error, browser software error, or the problem lays with the Web site. When an AI agent takes more of the end user tasks and operates through a less deterministic model than a web browser, there is a significant risk of exposing users to an unreliable and untrustworthy platform. The risk will likely be compounded as the user's AI agents interact with a Web site's AI agents.

Another assumption that AI web user agents are proving fragile is the relatively clean delineation between browsers and crawlers. When crawlers emerged in the early days of the Web, the impact of their automated web page access on web servers led to the creation of the `robots.txt` proposal indicating which pages to crawl and limiting the frequency of access. In practice, there were only so many crawlers deployed at web scale that this proved sufficient in keeping the induced load on servers manageable.

AI agents conducting deep research tasks for the end users can fetch many pages in quick succession in a completely distributed fashion across the population of end users (as recently painfully felt by a number of open source documentation  websites). Where `robots.txt` was meant to manage the impact of a few non-human directed crawlers, it is unlikely to be fit for purpose for widely distributed, user-directed crawling agents (which may not be easily recognizable as traditional crawlers). Without a standard in place for managing these interactions, anti-AI firewalls have started to emerge, which creates friction and requires more resources. We see standardization opportunities to support responsible actors that wish to work together to reduce ecosystem costs.

Risks:

* AI Agents weakens the ecosystem by ignoring lessons from Web user agents duties
* AI Agents get widely adopted before their security architecture make them safe

Opportunities:

* Define crawling behaviors for human-directed user agents
* AI Web Agents remove incentives behind high-friction Web user experience (ads, modals, permissions, …)

# AI Agents and the Developer Experience

One domain where AI Agents seem to be gaining rapid adoption is in coding environments. The impact of most Web technologies ultimately depends on how well and rapidly Web developers can make use of them: what impact coding AI Agents might have on adoption of W3C's work?

Today, the following elements are parts of the adoption path for developers:

* Awareness that the said technology or feature exists,
* Availability and quality of implementations, from experimental to shipped interoperably (as recognized e.g. by "[Baseline, widely available](https://web-platform-dx.github.io/web-features/)" label for Web features)  
* Availability of documentation and training material,  
* Availability of coding support (e.g. IDE autocompletion, templates, refactoring),  
* Availability of supporting libraries and frameworks,  
* Ease of integration into existing systems (e.g. a payment technology needs to work with existing payment workflows).

Coding AI Agents already and will soon be able to:
* Propose specific technologies or features (or even code) to accomplish a given task.
* Propose or annotate code based on information on available implementations and the expected deployment target.  
* Summarize technical documentation tailored for a give context, or create a training program.
* Identify libraries and frameworks that help adopt a given feature (although their ability to do that at scale and without hallucinations remains uncertain).
* Guide feature integration within an existing workflow or system based on the patterns it might have identified in its training set.

As with any other domain, the utility and quality of AI tools for coding with Web technology depends on **accurate**, **up-to-date** information. Because the Web is large, and constantly evolving without centralized control, relying on rapidly outdated materials incorporated at model training time may not yield good results. Instead, integrating curated information (e.g., using Model Context Protocol (MCP)) would ensure better outcomes.

Today's curated resources include:
* the [webref](https://github.com/w3c/webref/) project, a comprehensive repository of machine-readable data on browser technologies
* the [web features project](https://github.com/web-platform-dx/web-features/), catalog of descriptions of all browser features which the [browser-compat-data](https://github.com/mdn/browser-compat-data/) allows to associate with actual shipping implementations
* the [MDN documentation project](https://github.com/mdn/content/), curated technical reference documentation and training materials on these features, with a specific focus on accuracy, and integrating qualitative considerations about their usage (e.g., to support accessibility)


Packaging and distributing these resources with greater focus on their impact on existing and emerging AI Agents may help increase quality adoption of new web technologies. It may also pave the way for a broader conversation on how to integrate AI agents into other technology ecosystems.

Risks:

* Coding AI agents may suggest obsolete syntax, APIs, library versions, or other best practices

Opportunities:

* Coding AI assistants may make web development much more accessible

