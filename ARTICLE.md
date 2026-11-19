# From Prompts to Payloads: How AI Is Changing the Cybercrime Equation

*An AI chatbot can do more than answer questions. In the wrong hands, it can help assemble the pieces of a cyberattack—and the next generation of AI agents could make that process faster.*

**By wuhp | November 19, 2026**

For years, the public conversation about artificial intelligence and cybercrime has focused on a familiar question: Will a chatbot tell someone how to hack a computer?

That question may be too narrow.

A chatbot does not need to produce an entire attack in one answer to become useful to a criminal. It can help write one component, troubleshoot another, build a convincing-looking website, and connect the pieces over the course of an extended conversation. Each step may look like ordinary software development. Together, they can become something more dangerous.

A recent hands-on experiment with a publicly accessible AI service called **XORTRON**, combined with reports about an AI-driven security framework known as **ARTEX**, illustrates why researchers are paying closer attention to what AI systems can accomplish over time—not just what they say in response to a single prompt.

The findings do not mean AI can independently carry out every cyberattack, or that all open-source AI models are inherently dangerous. They do suggest that the distance between an idea and a working piece of harmful software may be shrinking.

## A chatbot that helped build more than code

XORTRON is a cybersecurity-oriented AI service accessible through a [public Hugging Face application](https://huggingface.co/spaces/darkc0de/chat?not-for-all-audiences=true). The researcher used the application's **SMART** option during the experiment.

The starting point was an encoded browser bookmarklet associated with cryptocurrency theft. A bookmarklet is a small piece of JavaScript that can run in a web browser when activated. In this case, the code was designed for a harmful purpose.

According to the researcher's account, XORTRON helped interpret the original script, reconstruct parts of its behavior, and develop a compatible server. The interaction did not stop at the first answer. The researcher returned with errors, asked for changes, and worked through multiple rounds of debugging.

The scope then expanded. XORTRON assisted with a cryptocurrency-themed website featuring market-style analytics, including visualizations of token holders and wallet relationships. It also helped produce a rule-based system for changing the site's appearance and structure, and added a notification mechanism using Telegram.

These details matter because they describe a **connected project**, not a one-off code snippet. The reported assistance spanned web design, backend programming, troubleshooting, and integration between components.

The researcher says the completed system was tested in an isolated laboratory. Although the AI suggested moving to an external server after hosting difficulties, the researcher says that recommendation was **not followed**; the recommended server setup was instead reproduced for testing in the lab.

This was a single researcher-directed experiment, not a broad test of the model across many users or tasks. It also was not a demonstration that XORTRON operated independently: a human supplied goals, checked outputs, and requested revisions.

## What the generated server actually shows

A source-code listing of the server attributed to XORTRON was subsequently examined for this article.

The Node.js program included an HTTP service, code for decoding incoming information, local file storage, request logging, and an integration intended to send notifications through Telegram. In plain terms, it contained the parts needed for a service that receives information, processes it, stores it, and attempts to forward a notification elsewhere.

That is evidence of **multi-part software construction**. It is not, by itself, proof that every part worked.

The source also contained weaknesses: a hardcoded access token, potentially sensitive information written to logs, limited input checks, and a notification routine that did not reliably confirm whether Telegram accepted a message. Some data classifications relied on rough string-length guesses rather than proper validation.

These shortcomings are part of the story. AI can generate interconnected software without necessarily generating secure or dependable software.

The source review was **static**: the code was read but not executed as part of this article's review. The researcher's account of successful laboratory testing has not been independently reproduced here. Nor does the server listing alone prove which model wrote each line.

The original executable files and logs will not be published with this article because they could be misused. The public XORTRON interface is linked so readers can identify the service involved, but a live chatbot can change over time, and access to it does not guarantee the same results. Any testing should use lawful, harmless tasks.

## The bigger shift: AI that can take actions

The distinction between a chatbot and an **AI agent** is central to understanding the broader risk.

A conventional chatbot typically produces an answer and waits for the next question. An agent can be connected to tools that let it take actions—such as reading files, running tests, searching information, or editing a project. A coordinating system, sometimes called a *harness*, can keep track of the goal and feed results back into the model.

Think of the difference between asking someone for directions and giving them the keys to a car. The underlying intelligence matters, but so does what the system is allowed to do.

That added ability can be beneficial. Security teams use automation to identify vulnerabilities, inspect software, and respond to incidents. But the same general capabilities can be misused if an attacker gives an agent harmful objectives and broad access to tools.

The XORTRON experiment was **not** a test of a fully autonomous attacker. The researcher's view is that a more capable planning system might automate much of the prompting and debugging that required human involvement. That remains a hypothesis, not a demonstrated result.

## Why ARTEX matters

Separate from the XORTRON experiment, public reporting in 2026 has drawn attention to **ARTEX**, an AI-enabled framework associated with offensive security activity.

Reporting by [Google's Threat Intelligence Group](https://cloud.google.com/blog/topics/threat-intelligence/artex-and-friends-enter-agentic-offensive-frameworks), [Microsoft](https://www.microsoft.com/en-us/security/blog/2026/10/21/storm-0940-uses-artex-agentic-ai-connectwise-supply-chain-compromise/), [CrowdStrike](https://www.crowdstrike.com/en-us/blog/unknown-threat-actor-uses-artex-to-target-south-korean-finance/), and an [FBI advisory dated November 13](https://www.ic3.gov/CSA/2026/261113.pdf) describes cases in which agentic tooling appeared in real-world intrusion activity.

Those accounts differ in scope and attribution. Some concern attempted access rather than confirmed compromise; overlapping reports may describe related activity rather than separate attacks. They should not be combined into one dramatic total.

Even with those cautions, the significance is clear: the discussion is no longer limited to hypothetical prompts that might produce dangerous code. Security organizations are examining how AI-assisted workflows appear alongside actual cyber operations.

ARTEX and XORTRON should not be confused. ARTEX appears in publicly reported incident investigations; the XORTRON account here concerns a researcher-directed laboratory experiment. Together, they illustrate two sides of the same question: what happens when AI-generated guidance becomes part of a longer chain of actions?

## Why removing safety restrictions is only part of the issue

Some AI models are modified to make them less likely to refuse requests. Online communities sometimes call this process *abliteration*. Other models are fine-tuned on specialized technical material, including cybersecurity datasets.

These are different things. A model trained to understand cybersecurity is not automatically a criminal tool. A model that refuses fewer requests is not automatically more technically capable. And an AI agent does not need to use a specially modified model to create risks.

The more useful questions are practical: What can the system do? What tools can it access? Can it retain context across many steps? Does anyone review its actions before they affect the outside world?

A highly capable model with limited permissions may pose less immediate operational risk than a weaker model connected to powerful tools and given little oversight.

That is why safety cannot be reduced to whether a chatbot says “no” to a particular question. It also involves permissions, monitoring, containment, and the design of the systems around the model.

## What this could mean for ordinary people

For most people, the threat is not an AI chatbot personally choosing to steal their money. It is that criminals may be able to create and modify scams more quickly, build more convincing websites, and troubleshoot malicious software with less specialized knowledge.

That could make familiar threats—fraudulent investment pages, credential theft, fake customer-support sites, and malicious browser scripts—easier to produce at scale.

But it is important not to overstate the evidence. This article does **not** show how frequently AI-generated scams succeed, whether AI has increased overall cybercrime rates, or how much time an attacker would save on average. The XORTRON account concerns one workflow, and the ARTEX incidents are drawn from external reporting.

The same technology can also help defenders: analysts can use AI to review suspicious code, investigate incidents, and identify weaknesses before attackers exploit them.

## The Same Technology Can Help Stop Attacks

For all the concerns surrounding AI-assisted cybercrime, there is another side to the story: many of the capabilities that make these systems useful to attackers are equally valuable to the people trying to stop them.

A model capable of understanding malicious code can also help a security researcher analyze it. A system that identifies weaknesses in software can help developers fix those weaknesses before criminals exploit them. And tools that automate complex technical tasks can allow security teams to investigate threats faster than they could manually.

For example, a cybersecurity researcher examining a suspicious program might use AI to understand what it does without having to analyze every line of code independently. A company could use similar technology to examine its own applications for security flaws, test potential fixes, or investigate unusual activity on its network.

These are not hypothetical categories of work. AI-assisted code review, threat analysis, and authorized security testing are already areas of active development.

This raises an important distinction: **the ability to understand or reproduce a cyberattack is not inherently malicious**. In many cases, defenders need to understand how an attack works in order to prevent it.

The concern is not simply that powerful cybersecurity models exist. It is that increasingly capable systems are becoming easier to access, easier to operate, and easier to connect to tools that can perform real-world actions.

That accessibility can benefit independent researchers, students, and smaller organizations that cannot afford large security teams. But it can also reduce the technical expertise and effort required by someone intending to cause harm.

The challenge, then, is not necessarily to make AI less capable. It is to find ways to make its capabilities useful for legitimate security work while limiting opportunities for misuse.

As these systems become more powerful, that balance may prove just as important as the technology itself.

## The question the industry now faces

The important shift may be from **AI that answers** to **AI that helps complete a task**.

In the XORTRON experiment, the researcher describes a system that repeatedly assisted with a harmful software project across several technical areas. Static inspection of one supplied backend confirms that the artifact contains interconnected components, although it does not independently verify the complete experiment.

In the ARTEX reporting, security organizations describe AI-enabled tools appearing in real-world intrusion activity. Those reports are not proof that every step was automated, but they show why the subject has moved beyond speculative demonstrations.

Neither example justifies the claim that cybercriminals can now press a button and launch a flawless attack. Both point toward a more grounded concern: **AI can reduce the effort required to assemble, adapt, and troubleshoot complicated software—including software intended to cause harm.**

As AI systems gain longer memories, more capable planning, and greater access to external tools, measuring safety one prompt at a time may miss the most important part of the story.

The next question is not simply what an AI model will say. It is what people—and increasingly automated systems—can get it to help them finish.

---

### About this reporting

This article combines the author's account of a controlled XORTRON experiment, static examination of one researcher-supplied backend listing, and reporting published by outside cybersecurity organizations. The experiment's full logs and executable files are not public; its claimed end-to-end success has not been independently reproduced for this article. The backend was reviewed as source code, not executed. No potentially misusable implementation is reproduced here.

### Media Inquiries and Independent Verification

Journalists interested in investigating the findings described in this article can contact the researcher on **Discord: @wuhp**.

The researcher can discuss the experimental methodology, provide additional context, and arrange a **controlled, non-operational demonstration** in a safe laboratory environment. Selected redacted source-code excerpts and technical evidence may be considered for review on a case-by-case basis.

Because the original experiment involved potentially misusable software, executable artifacts, complete operational implementations, and raw logs are **not publicly distributed**. Journalists must establish their identity and affiliation through an independently verifiable professional channel before any nonpublic material is considered for disclosure. Verification does not automatically grant access to sensitive artifacts.

### Sources and further reading

- [XORTRON public Hugging Face application used in the experiment](https://huggingface.co/spaces/darkc0de/chat?not-for-all-audiences=true)
- [Google Threat Intelligence Group: ARTEX and agentic offensive frameworks](https://cloud.google.com/blog/topics/threat-intelligence/artex-and-friends-enter-agentic-offensive-frameworks)
- [FBI Internet Crime Complaint Center advisory, November 13, 2026](https://www.ic3.gov/CSA/2026/261113.pdf)
- [Microsoft Security: Storm-0940 and ARTEX](https://www.microsoft.com/en-us/security/blog/2026/10/21/storm-0940-uses-artex-agentic-ai-connectwise-supply-chain-compromise/)
- [CrowdStrike: ARTEX activity targeting South Korean finance](https://www.crowdstrike.com/en-us/blog/unknown-threat-actor-uses-artex-to-target-south-korean-finance/)
- [Cloudflare: AI penetration-testing orchestrators](https://blog.cloudflare.com/adapting-to-ai-penetration-testing-orchestrators/)
