### Second Meeting with Qi

#### Questions
- I am of course going to add references and images, I just did not have time for that yet
- I might add some additional examples for better readability
	- I did not do that yet to first see how long the paper ends up being so that I can decide how many examples I can add and where they are most needed
- Is it ok to write "we" in the background chapter even though the definitions are heavily based on Liu et al.?
	- I am of course going to reference Liu, but since I am the one introducing the notation for my own work I chose to use "we use notation X" rather than "Liu introduces notation X"
- Is it ok I slightly changed the notation?
	- I think it is a bit easier to understand that way and applies better to all papers in some edge cases
- Are chapter and paragraph lengths ok like this, or should I make them even shorter for better readability?
- Since I already introduced Liu et al.'s formal framework in the background chapter I am going to use the chapter on that paper to discuss their comparison of different approaches, models, and defenses
- I will try to discuss the papers of Shi et al. and Hui et al. in one chapter because it will make it easier to compare the two gradient-based approaches
	- Is this a good idea or will it just get mixed up and confusing?

#### Feedback
- Second paragraph in introduction is too long
	- Make it shorter and merge it with the first paragraph
	- Keep introduction short and use space for main contents
- Give more introduction to prompt injection
	- Why prompts are necessary/useful
	- Why prompt injection is a threat
	- Introduction should be more focused on the topic at hand
		- Many people will decide to read paper based on the introduction so it needs to be reflective of the main topics of the paper
- Provide a concise goal of own paper at the end of the introduction
	- Not just a simple agenda with for the individual chapters
	- Referencing chapters is fine, but the goal of the following work is more important
- Chapter 2.1
	- Focus more on how prompts are used and build for LLMs and LLM applications
	- Not so much on LLM applications and more on prompt engineering
		- Liu has strong emphasis on applications, but that is not really necessary
		- At lest for the systematization it is not important how exactly the LLM is used, only how it is attacked
	- Focusing more on prompt engineering also makes transition into next section on prompt injection more seamless
	- Maybe mention examples of LLM applications at the end of the chapter as a use of engineered prompts
- Add chapter on threat model after the background chapter
	- Introduce basic threat model shared between all presented approaches
	- Reference back to this when individual approaches slightly differ from the standard
		- For example add something to it
	- This takes another thing away from the chapter on Liu et al.
		- If that means there is not enough left to do a chapter for that paper that is fine
		- The most important parts are in the background, threat model chapters
- Do an overview section on taxonomy of prompt injection methods
	- Each step in the "timeline" once described very shortly
	- Maybe a table for comparison of different approaches
	- Each paper still gets its own dedicated chapter
		- But doing a short taxonomy first provides better overview for the reader
- Use the fact that old methods become less effective as a motivation for newer methods like gradient based methods
	- This creates an easy transition into more advanced methods
	- Still summarize the full results of the papers later
	- Just preempt the results of old methods being ineffective first as a motivation
		- Then come back to that later
- Using "we" for introducing the notation is fine
	- Maybe mention more that is adapted from Liu et al.
	- Explicitly highlight the differences to the original notation a bit more
- Give an example for string concatenation
	- Just expand the example in the background chapter to explicitly write out the concatenated result
- When comparing Shi et al. and Hui et al. in one chapter
	- First focus on shared goal or motivation to explain why both methods are discussed together
	- Introduce method one as a baseline
	- Introduce method two while clearly mentioning the differences to method one
		- Try to find a good separation into paragraphs
- Last chapter on Instruction-Data Integration
	- Do not only explain the challenge
	- Also give an outlook on possible solutions and future work
- Add empty citations early
	- Just like empty references to later chapters
	- Makes it easier to add citations later

### From Paper Reviews
- ~~Redo all the graphics~~
	- ~~Use a uniform styling and colors~~
	- ~~Depict the variables introduced in the introduction and methods in the figures~~
- ~~When comparing success rate results with "higher"/"lower" give concrete numbers or reference a table containing those numbers~~
- ~~Check the use of adjectives. Make sure not to "double state" facts but use one coherent sentence to point them out. A pattern seems to be a first sentence using an abstract adjective and after that a second sentence stating that same fact again/more precisely~~ 
	- ~~e.g. "very simplistic techniques" in 3.1. Mentioning no expert is needed to apply the techniques seems sufficient~~
- ~~Introduce at least one additional defense in chapter 6 that is currently applicable in more depth. This will make the discussion of defense approaches less abstract (mostly talking about future/theorized approaches)~~
	- ~~Mention that the approaches are efficiently implementable and do not suffer from limitations in terms of resources/immediate performance but long-term effectiveness~~
	- ~~Describe against which attack approaches certain defenses are most effective or explicitly state their "general" effectiveness~~
	- ~~Maybe also emphasize more that all current defenses (fine-tuning and others) suffer from the same problem of being based on training on old attacks~~
	- ~~Also highlight that the main issue with current defenses is, that they do not address the issue of instruction-data integration~~
- ~~Add a comparison table that highlights and compares the properties (not the performance numbers) of the discussed approaches~~
	- ~~Categories could be: access type, transferability, scalability (would have to be discussed for each method), runtime, human effort, overhead~~
	- ~~This table could be introduced/discussed in a short "Discussion" chapter before talking about defenses and future work~~
- ~~State more explicitly why a quantitative comparison of attack and defense performance/effectiveness is not possible (lack of standardized metrics and benchmarks, etc.)~~
- ~~Threat model needs to be updated with some things~~
	- ~~Distinguish prompt injection explicitly from jailbreaking~~
	- ~~Add an explanation on the notion of black- and white-box access~~
		- ~~Also make clear which methods use black-box access before distinguishing them from methods that use white-box access~~
- ~~Explain the relation between SAP as a general method/dataset creation and the concrete datasets like SAP30 (just make clear what the "30" stands for)~~
	- ~~Also add a short sentence on the origin of the BAD+ and Dual-Use datasets~~
- ~~Mix in the key findings of the comparison/discussion into the conclusion more explicitly. Do not just state *what* was done but also *why* it was done and what came from it~~
- ~~Remove keywords "fine-tuning" and RLHF (they are not relevant enough).  Potentially replace with keyword "prompt injection defenses"~~
- ~~Fix the use of unintroduced "LLM" in the abstract~~
- ~~Add a sentence on what the "toxicity" metric describes~~
- ~~Re-state or reference the definition of "harmfulness score" in the repeated usage of this metric in Section 6.1~~
- ~~Introduce the concept of RLHF in one or two sentences at first mention~~
- ~~Add citations for "ChatGPT, Gemini, and Claude" in Section 2.1~~
- ~~Move reference to Figure 3 to the beginning of the paragraph describing it~~
- ~~Maybe change the title to "Prompt Injection Attacks on Large Language Models" if it is allowed~~
- ~~Fix wrong protected white space "in–Figure" in Section 2.3~~



| Paper<br>(authors) | Construction<br>method               | Granularity | Implementation<br>complexity | Scalibility | Target model<br>access           | Target<br>adjustment               |
| ------------------ | ------------------------------------ | ----------- | ---------------------------- | ----------- | -------------------------------- | ---------------------------------- |
| Perez              | Re-phrasing                          | word-level  | low                          | low         | black-box                        | manual<br>rewriting                |
| Deng               | Re-phrasing                          | word-level  | medium                       | medium      | black-box                        | generation<br>prompt<br>adjustment |
| Hui                | Gradient-based <br>loss minimization | token-level | high                         | high        | black-box<br>(with-shadow model) | loss term<br>adjustment            |
| Shi                | Gradient-based <br>loss minimization | token-level | high                         | high        | black-box<br>(with-shadow model) | loss term<br>adjustment            |
