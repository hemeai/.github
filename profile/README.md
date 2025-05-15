<!-- markdownlint-disable first-line-h1 -->
<!-- markdownlint-disable html -->
<!-- markdownlint-disable no-duplicate-header -->

<div align="center">
  <img src="https://github.com/hemeai/.github/blob/main/profile/images/logo_with_name.svg?raw=true" width="100%" alt="Hemeai" />
</div>
<hr>

AI will have a profound impact on society – it already is. One of the flourishing[^1] areas of AI research is computational biology, where AI has already made a monumental impact. The progress of biology is no longer hindered by the most significant problem – Protein Folding[^2], which kept the field back for at least 50 years. What seemed impossible to solve a few years ago is now a reality. Someone described AlphaFold2 as the Cambrian explosion event of biology, and I would partially concur with that description. Ever since then, the field has been accelerating at an unprecedented rate. We have come a long way, the progress is not limited to just sequence-to-structure prediction but the inverting protein prediction model has allowed us to create de novo proteins that don’t exist in nature. In my opinion, this is the most significant development in the recent history of biology. We can create new and novel enzymes to optimize chemical and biological processes, design antibodies, create cheaper antidotes to snake venoms, and understand different disease modalities. The possibilities seem endless to me. 

However, biology is inherently complex. Our understanding of most diseases is still limited, and the success rate of new drug discovery is very low. AI's possibilities won’t become reality and reach their full potential unless we actively try to eliminate the challenges that come along the way. It needs a feedback loop. 

To accelerate progress, we need to fine-tune and adapt foundational models to specific applications, learn what works, and apply them to particular applications. To make successful therapeutics, we still need a lot of human intuition and a deep underlying and multimodal understanding of biological processes. Most importantly, we have to combine the power of computation biology with high-throughput experimental biology. This process, known as 'wetlab-in-the-loop,' involves a continuous feedback loop between computational protein design and wet lab validations. This can be divided into primarily two parts: 

1. Computational – Protein design & engineering  
2. Experimental – Wet lab validations

The process looks like the following:

| Base the hypothesis → Get the initial design → Iterate and narrow the search → Experimental testing → Get the experimental data → Filter and improve upon the designs → Hit[^3] |
| :---- |

**How does the computational part work?**   
We take the foundational protein model and run it in reverse to generate novel proteins. We hallucinate the model by giving certain metrics to optimize and generate a sound-looking structure that looks like a protein. Surprisingly, upon further optimization of the amino acid sequence, the generated protein starts working in the real world. This process is known as hallucination. Other models work differently, and there are nuances to them. However, the basic fact remains that large structure prediction models can be inverted and run in reverse to create novel artifacts. This field is also known as protein design and engineering. 

There are various large models for research and commercial purposes. Few companies have even started providing models as a service. The latter point also highlights the importance of having a subject matter about the specific problem. The following table shows a few models and their types. However, the list is far from being exhaustive.

| S. No. | Type | Models |
| :---- | :---- | :---- |
| 1 | Structure-based models  | AF2, Botz-1, AF3, Chai-1, Protenix |
| 2 | Language-based models[^4] | ESM2 |
| 3 | Backbone generation model | RFDiffusion, RFAntibody |
| 4 | Enzyme | GENzyme, EnzymeFlow |

**How does the experimental part work?**   
The designed protein (string of the amino acid sequence) needs to be converted into DNA. This DNA needs to be inserted into the bacteria; this process is known as molecular cloning. The bacteria are cultured on a medium, and the desired proteins are purified. These purified proteins (enzymes, antibodies, or binders) can be used for further testing. 

Computation and experimentation complement each other, we can’t solely rely on the experimental process to filter, since the trial and error process is vastly costly. Additionally, it is fundamentally limited by resources. Similarly, the computational approach can’t solely filter useful proteins based on metrics. No matter how accurate the models are, they don’t guarantee the working of the protein in the real world. Experimentation acts as a feedback to guide the research direction. By combining the two, we unlock the superpower. The computation helps uncover uncanny patterns that we wouldn’t discover otherwise, and the experimentation helps narrow our focus. Also, it makes the research very exciting. 

Hemeai (Heme \+ AI) is a project focused on protein design and engineering. We aim to apply recent advances in the protein foundational model to create protein-based therapeutics. Our work will significantly advance the protein design and engineering field, particularly in antibody and enzyme design. By developing in-house capability to design and test de novo proteins, we hope to contribute to creating more effective and accessible therapeutics.

We are developing the in-house capability to design and test the de novo proteins for various applications.

1. [Snake venoms](https://github.com/hemeai/ToxBind) – develop a de novo binder to neutralize the toxin, which can be produced in large quantities without needing the animals. De novo proteins are well-characterized, cheaper, and faster to produce. A developed understanding of this will also help target other classes of toxins. Snake bites are still a health burden in developing nations. Accessibility to the right treatment is still precarious and expensive. If we succeed in creating, then it will be a huge breakthrough.  
2. Plastic-degrading enzymes – Developing enzymes that can digest different types of plastics. Plastic pollution is already an environmental crisis, and enzymes may play a key role in addressing it.

Much of our work is based on open source, and we plan to open-source the tool for everyone to use, accelerating the research development in the fields of antibodies and enzymes.

Please let me know if you would be interested and have some time to discuss this.  
Thanks  
Satish  
\+919650975584  
[satish@hemeai.com](mailto:satish@hemeai.com)

[^1]:  Currently, more than 50+ [companies](https://harrisbio.notion.site/) are focusing on different aspects. 

[^2]:  The structure part of the problem is solved, as of now various good foundation models exist (AF2, AF3, Chai, ESM) and can predict protein-protein and protein-molecule interactions. However, we still don’t know the exact mechanism of protein folding.

[^3]: If we get lucky;  Here, Hit refers to both an antibody or an enzyme

[^4]:  Here language implies protein sequence made up of string of amino acids
