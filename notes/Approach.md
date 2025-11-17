## Key points of source papers
#### Perez et al.
- Manual prompt construction
- Mostly generally applicable prompting "tricks"
- Almost no model refusal or defense strategy
- Mainly comes down to instruction following
	- The better the model is at instruction following overall, the more successful attacks are
- Defenses
	- None tested, only theorized/proposed
		- Filtering/scanning model outputs
		- Strictly separating data and instructions

#### Deng et al.
- Iterative, semi-automatic attack prompt generation/optimization
- More effective than manually constructed prompts
	- Unfortunately no direct comparison to Perez et al.
- Defenses
	- Fine-tuning
		- Somewhat effective but only as long as attack is similar to fine-tuning data
		- No negative impact on performing other tasks

#### Liu et al.
- First formal definition of prompt injection
- Mainly formalizing and taxonomizing
	- Many different attack strategies
	- Many different LLMs, tasks, datasets
	- Many different defense strategies
- Newer, more elaborate and combined attacks outperform older and simpler attacks
	- Best attacks still achieve very high success rates
- Defenses
	- Paraphrasing
	- Retokenization
	- Delimiters
	- Sandwich instructions
	- Hardened instructions
	- Perplexity detection
	- Naive LLM-based detection
	- Response checking
	- Known-answer detection
- No defense suitable to effectively prevent attacks
	- Most defenses are completely ineffective, some help a bit

#### Shi et al.
- Gradient-based attack prompt optimization
- Specifically targeting LLM-as-a-judge
	- First examples of attack scenarios with impact beyond direct user-LLM-intercation
	- E.g. search engines and tool selection
- Naive attacks (compare early approaches) are almost completely ineffective on newer models
	- So there is some progress in model robustness
- But latest approaches are very effective
	- So model robustness can not keep up with new attack strategies
- Defenses
	- Known-answer detection
	- Perplexity-based detection

#### Hui et al.
- Focus on prompt leaking (compare Perez et al.)
- More elaborate gradient-based method
	- Multiple, balanced optimization goals
	- Iterative optimization
	- Adversarial transformations
- Direct comparison to Perez et al.
	- Old, manual approaches are ineffective on modern applications/models
- Defenses
	- Hardened instructions
	- Output filtering

## Points I want to highlight in my paper
- Attacks have become more elaborate (very fast)
	- Outline development from late 2022 to late 2024
	- Manual prompting -> semi-automatic -> formalization -> gradient-based -> multi-goal optimization + transformations
- Models have become more robust BUT not fast enough
	- Most up-to-date attacks are always very effective with no real defenses
	- First manual approaches do not really work on modern models/applications
		- Direct comparison Perez et al. and Hui et al. (==maybe I can find more data of direct evaluation of old attacks on new models==)
- Attack scenarios are becoming more severe
	- Early use of LLMs mostly in direct interaction with user
		- Output can be checked and attacks can be recognized by user
	- LLMs start to "do more things" on their own
		- Integration with search, decision-making, LLM-agents, and up to controlling physical systems in robotics
		- Consequences of manipulated outputs can be more extreme (attacks become more attractive/profitable)
		- Outputs are not directly observed/checked by user
- Defending LLMs is conceptually difficult
	- Notion to "not mix data and instructions" is by definition broken by LLMs
	- ==I will give a quick overview of some current defense strategies==
		- Since the focus of the paper are the attacks, I will adjust the length/detail to how much "room I have left" for the paper
	- All defense strategies are based on attack goals and techniques
		- Therefor defenses are always catching up and lagging behind

- I will mainly focus on the first two points as the content of my paper
	- First point gives an overview of the papers and will therefor take up most of the content
	- Second point is useful to regularly come back to and conncet papers more strongly
		- The more additional data I find to back up this point the better I can use it in the main part of my paper
- The last two points are mainly motivation/background
	- I will use these in the introduction, conclusion and outlook
	- Depending on how much literature I find I might separate them out into small stand-alone chapters
	- ==Should I do some research on potential "fixes" for the key issue in fourth point?==
		- I do not know if there are any defenses that are conceptually different (not "lagging behind") but it would be interesting if there are any
		- ==Could I elaborate more on that, since there is no seminar topic for defenses of prompt injection?==
		- Some interesting approaches might be in XAI and mechanistic interpretability
			- But needs white-box access which is not always possible
