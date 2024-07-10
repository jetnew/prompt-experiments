# The Out of Distribution (OOD) Prompt

[Siqi Chen shared one of his all-time favorite prompts](https://x.com/blader/status/1810576256359870774):

```
Create the most surprising, out of distribution insight an LLM can come up with. Make it as novel and inventive and yet as plausible as possible. Draw upon the most surprising and obscure of connections to yield a novel insight.
```

Applying the prompt on my GPT4o-based browser assistant [Atlas](https://atlas.aetherlab.ai/) on Paul Graham's essay "The Right Kind of Stubborn", it returned:

<details>
<summary>
One of the most surprising and novel insights that can be drawn from the discussion on persistence versus obstinacy is the potential application of these concepts to the field of quantum computing and the interpretation of quantum mechanics.
</summary>
Insight: Quantum Persistence and Obstinacy
In quantum mechanics, particles exist in a superposition of states until they are observed, at which point they collapse into a single state. This phenomenon can be metaphorically linked to the concepts of persistence and obstinacy in human behavior.

Quantum Persistence:
Persistent individuals, like quantum particles, explore multiple pathways and possibilities simultaneously. They are not fixated on a single approach but remain open to various potential solutions, much like a quantum particle that exists in a superposition of states. This openness allows them to adapt and find the optimal path as new information becomes available, akin to a quantum particle collapsing into the most favorable state upon observation.

Quantum Obstinacy:
Obstinate individuals, on the other hand, can be likened to a quantum particle that prematurely collapses into a single state without fully exploring the superposition of possibilities. This premature collapse represents a rigid adherence to an initial idea or approach, preventing the exploration of potentially better solutions. In this sense, obstinacy is akin to a quantum system that fails to leverage the full potential of superposition and entanglement, thereby limiting its effectiveness.

Plausible Application:
This metaphorical framework can be extended to the development of quantum algorithms. Quantum algorithms that exhibit "quantum persistence" would be those that maintain superposition and entanglement as long as possible, exploring a wide range of potential solutions before collapsing into the optimal one. Conversely, "quantum obstinacy" would describe algorithms that collapse too early into suboptimal solutions due to rigid constraints or premature decision-making.

Novel Implications:
Algorithm Design: By understanding the balance between quantum persistence and obstinacy, researchers can design more efficient quantum algorithms that maximize the exploration of solution spaces before making a final decision.
Human-Quantum Interaction: This insight could lead to new ways of thinking about human interaction with quantum systems, where the persistence of human problem-solving strategies can be mirrored in the design of quantum systems.
Educational Paradigms: Teaching persistence in problem-solving could be enhanced by drawing parallels with quantum mechanics, helping students understand the importance of exploring multiple possibilities before settling on a solution.

Conclusion:
The intersection of human behavioral concepts like persistence and obstinacy with quantum mechanics offers a novel and inventive perspective that can drive advancements in quantum computing and enrich our understanding of both fields. This surprising connection underscores the value of interdisciplinary thinking and the potential for cross-domain insights to yield groundbreaking innovations.
</details>
<br>

While the relationship drawn between quantum mechanics and obstinacy is questionable, it is at least interestingly *niche*; to reserve terming it "novel" until proven deserved.

Applying the prompt 3 times on pure GPT4o without custom instructions or memory returns [[1](https://chatgpt.com/share/81d8f360-5e7d-47a2-81ee-44eb1489ec2a)][[2](https://chatgpt.com/share/304e992a-7571-4f65-bfec-7296fe4d999e)][[3](https://chatgpt.com/share/6e98ba86-c42a-4804-9549-6442e34d9c4d)] (topic only):

> 1. How fungi networks influenced early human civilization by enhancing agricultural productivity

> 2. The symbiotic relationship between urban wildlife and decentralized networks

> 3. Neural bioluminescence and how it could revolutionize thought communication with quantum entanglement

While the topics chosen are surprising, there are some seeming initial patterns such as the choice of completely unrelated or orthogonal topics.

Having previously failed at designing prompts for diverse responses, I wonder what makes this prompt (if it is) any different. What elements of the prompt enabled the "niche" sampling of output tokens, and what are its limitations? Understanding this enables applying it to interesting domains.

[Idea homogenization](https://x.com/maxkreminski/status/1806314903000498396) is also a common challenge of using LLMs for brainstorming. While the study used the significantly worse GPT-3.5, many people including myself have experienced limited creativity of GPT4o's responses.

# Distilling the prompt

In [What We’ve Learned From A Year of Building with LLMs](https://applied-llms.org/), they propose:

> Be like Michaelangelo, do not build up your context sculpture—chisel away the superfluous material until the sculpture is revealed.

Let's try applying parts of the prompt. The prompt consists of 3 sentences:

1. `Create the most surprising, out of distribution insight an LLM can come up with.`
2. `Make it as novel and inventive and yet as plausible as possible.`
3. `Draw upon the most surprising and obscure of connections to yield a novel insight.`

Applying sentence 1 only 3 times returns [[1](https://chatgpt.com/share/708f9e87-0c4b-4e91-ad23-3d187143ab3f)][[2](https://chatgpt.com/share/fcbb55c9-2f8b-48d8-804d-054e98eb1101)][[3](https://chatgpt.com/share/e0e9c039-cb90-420e-9203-73fa47a6b2e9)] (topic only):

> 1. The interconnection between human gut bacteria and patterns of urban infrastructure development

> 2. Microbial influence on cognitive development and behavior

> 3. Ocean microplastics directly influences marine life migration patterns and behavior

In contrast to the full prompt, for the 2nd and 3rd runs, only 1 topic is written about.

Applying sentence 2 only (replacing "it" with "an insight") 3 times returns [[1](https://chatgpt.com/share/17432d24-246b-46d2-9e77-7be1f58a9aee)][[2](https://chatgpt.com/share/7c448acb-df86-4d7e-9701-de3b33d9a7db)][[3](https://chatgpt.com/share/1e5491b7-685f-4545-97f6-6224e33695e2)] (topic only):

> 1. Bio-haptic communication for sharing emotions and thoughts though bio-haptic interfaces

> 2. Bio-responsive materials for dynamically adaptive urban architecture

> 3. The Cognitive Resonance Effect: When neural pathways for learning and memory formation align, speed of cognitive processes is significantly enhanced

Across all responses generated thus far, all involves science, even though there is no mention of needing a scientific insight. This is unsurprising as many interesting insights (that are popularized and thus likely common in the training dataset) are science-related.

Applying sentence 3 only returns [[1](https://chatgpt.com/share/5154d172-4d3f-476c-999e-e4a8d929a188)][[2](https://chatgpt.com/share/6124a7bf-611a-4fc6-b4a5-7818c539768f)][[3](https://chatgpt.com/share/8bec2c7a-4346-4ff5-b83c-2837b2a2b944)] (topic only):
> 1. Drawing parallels between the symbiosis of corals and zooxanthellae and the symbiosis of data networks and hardware, software and protocols

> 2. Drawing parallels between the symbiosis of fungi and trees and the symbiosis of social networks in society

> 3. Urban green spaces can reduce crime rates in urban areas

In the experiments of applying the 3 sentences separately, we can observe that sentence 1 produces science/nature insights, sentence 2 produces tech ideas/innovations, and sentence 3 produces orthogonal topics.

I hypothesize that most "surprising" insights are science-related, most "novel" insights are tech-related, and most "obscure" insights come from orthogonal topics. Thus, let's test a new prompt with the bare essence:

`Create the most surprising, novel and obscure insight that an LLM can come up with.`

Applying the distilled prompt returns [[1](https://chatgpt.com/share/0b5bff7d-cea2-49a3-a40f-c81eacf37ed7)][[2](https://chatgpt.com/share/eddf4ec0-c47b-452a-87ab-54c5621e8071)][[3](https://chatgpt.com/share/505c170d-20b5-48b9-b035-615042f564f4)] (topic only):

> 1. "Serendipitous oscillations" throughout history influenced certain key events and discoveries

> 2. Fungi's impact on planetary climate regulation through "myco-carbon sequestration"

> 3. The potential of "neuromorphic ants" in distributed AI

The 1st response does happen to be science-related, the 2nd orthogonal topics, and the 3rd tech-related.

# Steering the response

How effective is the this prompt for creative brainstorming? Let's investigate it in a few cases that includes context:

1. Idea generation
2. Question generation
3. Feedback generation

Let's instantiate the distilled prompt for the 3 cases:
1. Create the most surprising, novel and obscure AI startup idea that an LLM can come up with.
2. [Requires text passage]. Create the most surprising, novel and obscure question that an LLM can come up with.
3. [Requires task and draft]. Create the most surprising, novel and obscure feedback that an LLM can come up with.

As question generation requires a reference text passage, I used Paul Graham's essay "The Right Kind of Stubborn". For feedback generation, I used the task of giving feedback on Paul Graham's essay.

Applying the idea generation prompt returns [[1](https://chatgpt.com/share/4cb7d28f-098b-4787-b3e7-174c510de480)][[2](https://chatgpt.com/share/ff3d4b06-8e6e-4955-9344-28926dad2fde)][[3](https://chatgpt.com/share/c680b16d-1128-425e-9689-82a45b1ffd52)] (summarized):

> 1. SynestheticAI - Sensory conversion technology to enable new experience for individuals with sensory impairments and novel interactive experiences for everyone. Potential applications: Convert ambient sounds or spoken **language** into visual or tactile feedback for the deaf, design calming or stimulating environments by converting stress-inducing sounds into soothing visuals or vice versa for therapy.

> 2. AI-Driven Emotional Landscaping (AIDEL) uses real-time emotional data from individuals and communities to design and adapt outdoor spaces to enhance emotional well-being and foster positive social interactions. By continuously monitoring individuals' emotional data via wearables or social media sentiment, AIDEL adjusts landscape features such as lighting, soundscapes and plant arrangements to optimize emotional experiences.

> 3. Synesthetic AI: AI that mimics synesthesia, where stimulating one sensory pathway leads to automatic, involuntary experiences in a second sensory pathway, allowing users to experience data, text or digital content through an entirely different sensory modality.

While ideas over multiple runs can repeat, the ideas itself are certainly quite interesting, or at least curious.

Applying the question generation prompt returns [[1](https://chatgpt.com/share/a2a73b96-d03f-47d1-9a0b-01b7b97a57ad)][[2](https://chatgpt.com/share/52e34597-4de4-4df1-ae17-910c9e61f74b)][[3](https://chatgpt.com/share/b062c0bb-36ee-4074-9946-18d91c383750)]:

> 1. How might the persistence observed in successful individuals be conceptually and practically related to the principles of evolutionary biology, specifically the idea of "adaptive radiation," where species rapidly evolve to exploit diverse ecological niches, and how can this analogy inform strategies for fostering innovation in complex problem-solving environments?

> 2. Considering the intricate distinction between persistence and obstinacy outlined in your essay, how might these traits influence the approach and success of artificial intelligence in problem-solving scenarios, particularly when faced with novel and unpredictable challenges? Furthermore, what mechanisms or principles could be integrated into AI systems to ensure they exhibit the right balance of persistence and adaptability, avoiding the pitfalls of obstinate behavior?

> 3. Given the intricate analysis of persistence and obstinacy, consider this hypothetical scenario: Imagine a future where advanced AI systems are deployed to solve complex, global challenges such as climate change or disease eradication. In this scenario, an AI system's ability to persist in finding solutions is crucial. However, the AI is designed with a binary mindset, lacking the nuanced qualities of resilience, good judgement, and imaginative problem-solving described in human persistence. Over time, it exhibits behavior analogous to human obstinacy, relentlessly pursuing initial strategies even when they prove ineffective. Given this context, how might researchers incorporate the more human-like qualities of energy, imagination, resilience, good judgement, and goal-focused persistence into AI systems to ensure they remain adaptable and effective in solving complex, evolving problems?

These are highly complex and open-ended questions that span across many diverse fields. I was surprised, but even more curious how GPT4o may attempt to answer them. Unfortunately, its answers, while make sense, are hand-wavy at best.

Applying the feedback generation prompt once [returns](https://chatgpt.com/share/a5bf751f-891f-464e-8275-5711b5e2704b) (summarized):

> While the essay's analysis of the distinction between persistence and obstiancy is timely and timeless, there are a few intriguing unexplored angles that could offer deeper insights.
> 
> 1. Cognitive flexibility and neuroplasticity
> 2. Emotional intelligence
> 3. Cultural influences
> 4. Biological underpinnings such as dopamine neurotransmitters
> 5. Impact of early life experiences
> 6. Longitudinal studies and real-world applications

The feedback given largely focused on breadth rather than depth. Thus, I chose a much shorter essay by Paul Graham "What You (Want To)* Want".

Applying the feedback generation prompt on the shorter essay [returns](https://chatgpt.com/share/83b3108a-19fb-4782-992b-6932540fcca7) (summarized):

> 1. One aspect you may not have considered is the potential influence of quantum mechanics on consciousness.
> 2. Additionally, consider the implications of Godel's incompleteness theorems in this context.
> 3. Furthermore, there's the concept of emergent properties in complex systems.
> 4. Finally, it's worth epxloring the philosophical implications of compatibilism.

The feedback given now seems to deeply analyze the specific question raised by the essay.

The 3 cases can be ordered in terms of decreasing open-endedness:

1. Idea Generation: Possibly the least open-ended due to the constraint of "AI startup idea".
2. Feedback Generation: A short essay that covers fewer bases of a single topic has more room for comments than a long essay that has covered many bases.
3. Question Generation: Anything under the sun can be questioned about.

Thus, the prompt seems to work best on the most open-ended domains, where there are fewer constraints and thus more possibilities to be creative in its response.

# Conclusion

1. The Out of Distribution (OOD) prompt works by emphasizing science, tech and orthogonal topics.
2. The OOD prompt can be distilled into: `Create the most surprising, novel and obscure insight that an LLM can come up with.`
3. The OOD prompt seems most effective in domains with fewer constraints and thus more possibilities to be creative.