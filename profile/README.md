<!-- markdownlint-disable first-line-h1 -->
<!-- markdownlint-disable html -->
<!-- markdownlint-disable no-duplicate-header -->

<div align="center">
  <img src="https://github.com/hemeai/.github/blob/main/profile/images/logo_with_name.svg?raw=true" width="100%" alt="Hemeai" />
</div>
<hr>

AI will have a profound impact on society – it already is. One of the flourishing[^1] areas of AI research is computational biology, where AI has already made a monumental impact. The progress of biology is no longer hindered by the most significant problem – protein folding, which has kept the field back for at least 50 years. What seemed impossible to solve a few years ago is now a reality. Someone described AlphaFold2 as the Cambrian explosion event of biology, and I would partially concur with that description. Ever since then, the field has been accelerating at an unprecedented rate. We have come a long way; the progress is not limited to just sequence-to-structure prediction, but the inverting protein prediction model has allowed us to create de novo proteins that don’t exist in nature. In my opinion, this is the most significant development in recent biological history. We can create new and novel enzymes to optimize chemical and biological processes, design antibodies, develop cheaper antidotes to snake venoms and gain a deeper understanding of different disease modalities. The possibilities seem endless.

<div align="center">
  <img src="https://github.com/hemeai/.github/blob/main/profile/images/landscape.png" width="100%" alt="design process" />
</div>

However, biology is inherently complex. Our understanding of most diseases is still limited, and the success rate of new drug discovery is very low. AI's possibilities won’t become a reality and reach their full potential unless we actively try to eliminate the challenges that come along the way. It needs a feedback loop.

To accelerate progress, we need to fine-tune and adapt foundational models to specific applications, learn what works, and apply it to particular applications. To develop successful therapeutics, we still require a significant amount of human intuition and a profound, underlying, multimodal understanding of biological processes. Most importantly, we have to combine the power of computational biology with high-throughput experimental biology. This process, known as 'wetlab-in-the-loop,' involves a continuous feedback loop between computational protein design and wet lab validations. This can be divided into primarily two parts:

1. Computational – Protein design & engineering
2. Experimental – Wet lab validations

The process looks like the following:

| Base the hypothesis → Get the initial design → Iterate and narrow the search → Experimental testing → Get the experimental data → Filter and improve upon the designs → Hit[^2] |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |

<div align="center">
  <img src="https://github.com/hemeai/.github/blob/main/profile/images/design_process.png" width="100%" alt="design process" />
</div>

**How does the computational part work?**  
We take the foundational protein model and run it in reverse to generate novel proteins. We hallucinate the model by providing certain metrics to optimize and create a structure that resembles a protein. Surprisingly, upon further optimization of the amino acid sequence, the generated protein begins to function in the real world. This process is known as hallucination. Other models operate differently and have their nuances. However, the basic fact remains that large structure prediction models can be inverted and run in reverse to create novel artifacts. This field is also known as protein design and engineering.

There are various large models for research and commercial purposes. Few companies have even started providing models as a service. The latter point also highlights the importance of having a deeper understanding of the specific problem. The following table displays several models and their corresponding types. However, the list is far from being exhaustive.

| S. No. | Type                      | Models                             |
| :----- | :------------------------ | :--------------------------------- |
| 1      | Structure-based models    | AF2, Botz-1, AF3, Chai-1, Protenix |
| 2      | Language-based models[^3] | ESM2                               |
| 3      | Backbone generation model | RFDiffusion, RFAntibody, RFpeptide |
| 4      | Enzyme                    | ZymCTRL, ProteinMPNN               |

**How does the experimental part work?**  
The designed protein (string of amino acid sequence) needs to be converted into DNA. This DNA needs to be inserted into the bacteria; this process is known as molecular cloning. The bacteria are cultured on a medium, and the desired proteins are purified. These purified proteins (enzymes, antibodies, or binders) can be used for further testing and analysis.

Computation and experimentation complement each other; we can’t solely rely on the experimental process to filter, since the trial-and-error process is vastly costly. Additionally, it is fundamentally limited by resources. Similarly, the computational approach can’t solely filter useful proteins based on metrics. No matter how accurate the models are, they don’t guarantee the protein's functioning in the real world. Experimentation acts as feedback to guide the research direction. By combining the two, we unlock the superpower. The computation helps uncover uncanny patterns that we wouldn’t discover otherwise, and the experimentation helps narrow our focus. Also, it makes the research very exciting.

HemeAI is focused on protein design and engineering. We aim to apply recent advances in the protein foundational model to create protein-based therapeutics. Our work will significantly advance the field of protein design and engineering, particularly in the areas of antibody and enzyme design. By developing in-house capabilities to design and test de novo proteins, we aim to contribute to the creation of more effective and accessible therapeutics.

1. [Snake venoms](https://github.com/hemeai/ToxBind) – develop a de novo binder to neutralize the toxin, which can be produced in large quantities without needing the animals. De novo proteins are well-characterized, cheaper, and faster to produce. A developed understanding of this will also help target other classes of toxins. Snake bites remain a significant health burden in developing nations. Access to the right treatment is still precarious and expensive. If we succeed in creating, then it will be a huge breakthrough.

1. [Snake venoms](https://github.com/hemeai/ToxBind) – develop a de novo binder to neutralize the toxin, which can be produced in large quantities without needing the animals. De novo proteins are well-characterized, cheaper, and faster to produce. A developed understanding of this will also help target other classes of toxins. Snake bites remain a significant health burden in developing nations. Accessibility to the right treatment is still precarious and expensive. If we succeed in creating, then it will be a huge breakthrough.
1. Plastic-degrading enzymes – Developing enzymes that can digest different types of plastics. Plastic pollution is already a significant environmental crisis, and enzymes may play a crucial role in addressing it.

Much of our work is based on open-source software, and we plan to open-source the tool for everyone to use, thereby accelerating research and development in the field of protein engineering.

Please let me know if you're interested and have some time to discuss this.

[hi@hemeai.com](mailto:hi@hemeai.com)

[^1]: Currently, more than 50+ [companies](https://harrisbio.notion.site/) are focusing on different aspects.
[^2]: If we get lucky; Here, Hit refers to a protein (antibody, enzymes, or binders)
[^3]: Here language implies protein sequence made up of string of amino acids
