<!-- markdownlint-disable first-line-h1 -->
<!-- markdownlint-disable html -->
<!-- markdownlint-disable no-duplicate-header -->

<div align="center">
  <img src="https://github.com/hemeai/.github/blob/main/profile/images/logo_with_name.svg?raw=true" width="100%" alt="Hemeai" />
</div>
<hr>

AI will have a profound impact on society – it already is. One of the flourishing[^1] areas of AI research is computational biology, where AI has already made a monumental impact. The progress of biology is no longer hindered by the most challenging problem – protein folding, which held back the field for at least 50 years. What seemed impossible to solve a few years ago is now a reality. AlphaFold2 is the Cambrian explosion event of computational biology, sprouting the birth of new, innovative protein structures from nothing. Ever since then, the field has been accelerating at an unprecedented rate. We have come a long way; the progress is not limited to just sequence-to-structure prediction, but we have started to create de novo proteins by running the model in reverse, which don’t exist in nature. In my opinion, this is the most significant development in recent biological history. The applications are immense, ranging from creating and improving enzymes to optimizing chemical and biological processes, designing better antibodies, developing cheaper antidotes to snake venoms, and gaining a deeper understanding of disease modalities. The possibilities seem endless to me. 

However, biology is inherently complex. Our understanding of most diseases is still limited, and the success rate is very low. AI's possibilities won’t become a reality and reach their full potential unless we actively try to eliminate the small challenges that come along the way. It needs a feedback loop. 

To accelerate progress, we need to fine-tune and adapt foundational models to specific applications, learn what works, and refine them. To increase the success rate, we still require a significant amount of human intuition and a deep understanding of the complex biological processes underlying them. Most importantly, we have to combine the power of computational biology with high-throughput experimental biology. This process, known as 'wetlab-in-the-loop', involves a feedback loop between protein design and wet lab validations. 

1. Computational – Protein design & engineering  
2. Experimental – Wet lab validations

The process looks like the following:

| Base the hypothesis → Get the initial design → Iterate and narrow the search → Experimental testing → Get the experimental data → Filter and improve upon the designs → Hit[^2] |
| :---- |

**How does the computational part work?**  
We take the foundational protein model and run it in reverse to generate novel proteins. We hallucinate the model by providing certain metrics to optimize and create a structure that resembles a protein. Surprisingly, further optimization of the amino acid sequence enables the generated protein to function in the real world. Other models operate differently and have their own nuances. However, the basic fact remains that large structure prediction models can be inverted and run in reverse to create novel proteins. This field is also known as protein design and engineering. 

There are various large models for research and commercial purposes. Few companies have even started providing models as a service. The latter point also highlights the importance of having a deeper understanding of the specific problem. The following table displays several models and their corresponding types. However, the list is far from being exhaustive.

| S. No. | Type | Models |
| :---- | :---- | :---- |
| 1 | Structure-based models  | AF2, Botz-1, AF3, Chai-1, Protenix |
| 2 | Language-based models[^3] | ESM2 |
| 3 | Backbone generation model, hallucination binders | RFDiffusion, RFAntibody, RFpeptide, BindCraft |
| 4 | Enzyme | ZymCTRL, ProteinMPNN |

**How does the experimental part work?**   
The designed protein (string of amino acid sequence) needs to be converted into DNA. This DNA needs to be inserted into the bacteria; this process is known as molecular cloning. The bacteria are cultured on a medium, and the desired proteins are purified. These purified proteins (enzymes, antibodies, or binders) can be used for further testing and analysis. 

Computation and experimentation complement each other; we can’t solely rely on the experimental process to filter, since the trial-and-error process is vastly costly. Additionally, it is fundamentally limited by resources. Similarly, the computational approach can’t solely filter useful proteins based on metrics. No matter how accurate the models are, they don’t guarantee the protein's functioning in the real world. Experimentation acts as feedback to guide the research direction. By combining the two, we unlock the superpower. The computation helps uncover uncanny patterns that we wouldn’t discover otherwise, and the experimentation helps narrow our focus. Also, it makes the research very exciting. 

HemeAI is focused on protein design and engineering. We aim to apply recent advances in the protein foundational model to create protein-based therapeutics. Our work will significantly advance the field of protein design and engineering, particularly in the areas of antibody and enzyme design. By developing in-house capabilities to design and test de novo proteins, we aim to contribute to the creation of more effective and accessible therapeutics. 

1. [Snake venoms](https://github.com/hemeai/ToxBind) – develop a de novo binder to neutralize the toxin, which can be produced in large quantities without needing the animals. De novo proteins are well-characterized, cheaper, and faster to produce. A developed understanding of this will also help target other classes of toxins. Snake bites remain a significant health burden in developing nations. Access to the right treatment is still precarious and expensive. If we succeed in creating, then it will be a huge breakthrough.

2. Plastic-degrading enzymes – Developing enzymes that can digest different types of plastics. Plastic pollution is already a significant environmental crisis, and enzymes may play a crucial role in addressing it.

**Enzymes**  
Proteins are the molecular workhorse of life. Enzymes are specific proteins that play a critical role in catalyzing reactions. Each living organism uses enzymes to catalyse the reaction. Traditionally, we have relied on biodiversity to get the required enzyme. However, those enzymes have evolved and perfected over millions of years and have their limits. They are mighty but often slow for many modern-day applications. Recently, protein language models have given new opportunities, given that the model is trained on millions of sequences. It can learn the representation of all proteins at once. Therefore, when applied to new enzymes, it suggests amino acids change without affecting the catalysis part, often improving many desired outcomes like thermostability, activity, and selectivity. 

Why De Novo Designed Enzymes?

- Tailored for specific reactions, even ones not found in nature   
- More stable, active, or selective under extreme industrial conditions 

The key applications by sectors are the following:

| Sector | Use Case | Market Demand |
| :---- | :---- | :---- |
| Pharmaceuticals | Chiral synthesis, biocatalysis for APIs | High |
| Food & Beverage | Flavor development, lactose breakdown, brewing enzymes | High |
| Biofuels & Energy | Cellulases, lipases for biodiesel and biomass | Moderate |
| Detergents | Proteases, amylases for stain removal | High-volume, low margin |
| Textile & Leather | Enzymes for softening, bleaching, depilation | Niche but steady |
| Agriculture | Soil enrichment, plant health (e.g., nitrogenase mimics) | Emerging |
| Plastics & Waste | PET-degrading enzymes, compostable polymer recycling | High innovation potential |

Ubiquitous application in many sectors presents opportunities. However, it also presents many challenges. Some of the challenges we highlight here:

1. Activity prediction: De novo-generated proteins are filtered based on specific metrics and validated by comparing their multidimensionality to that of real-world systems. New models are still in their infancy; they tend to overfit, generating proteins that are confident metrics but don't work in the wet labs. This recent paper by The [Align Bio Foundation](https://alignbio.org/) [highlights](https://arxiv.org/abs/2507.22210) the need for the right quality and quantity of protein for the protein language model.   
2. Stability: Industrial processes often operate at high pH levels and temperatures. Macromolecules like enzymes denature at high temperatures and tend not to work at extreme pH, losing their enzymatic properties. Even a minute variation in the molecular structure of the enzymatic pockets can render it functionally useless.   
3. Regulations: Especially in food/agri applications.  
4. High R\&D Cost: Currently, there is no computational method that can generate tailor-made proteins/enzymes for specific applications. Although computational methods aim to reduce trial-and-error, they can sometimes have the opposite effect, thereby increasing R\&D costs. 

**Antibodies**  
Antibodies are large, Y-shaped proteins produced by B-cells as a primary immune defence. It binds explicitly to unique molecules of a pathogen, called antigens. Each Y unit contains two identical copies of a heavy chain (H) and two identical copies of the light chain (L); they differ in their sequence and length. The top of the Y shape contains the variable region (V), also known as the fragment antigen-binding region, called Fab. This part binds to a specific part of the antigen called “epitope”. The bottom part of the Y unit is called the FC region (fragment crystallizable). It is responsible for providing binding sites to other immune cells. The antigen-binding site is called “paratope”; they are held together by complementarity-determining regions (CDRs), which are specific loops within the variable regions of antibodies that are crucial for antigen binding. The particular arrangement of amino acids (paratope) within the CDRs determines the shape and binding affinity of the antibody for its target antigen. Variations in CDRs are essential for the diversity and specificity of the immune response. 

Antibodies are the dominant class of protein therapeutics, with over 160 antibody therapeutics currently licensed globally and a market value expected to reach $445 billion in the next five years. Most AI algorithms are focused on sampling CDR loops while targeting any specified epitope or any target of interest. The lack of data hinders progress in this space. The following describes the key application area: 

| Application Area | Description | Market Demand |
| ----- | ----- | ----- |
| Cancer Immunotherapy | Checkpoint inhibitors, CAR-T/NK engagers, ADCs | Very high |
| Autoimmune Diseases | TNF inhibitors, IL-6 blockers, B-cell depletion | High |
| Infectious Diseases | Neutralizing antibodies (e.g., COVID, RSV, HIV) | Moderate |
| Rare/Orphan Diseases | Designer antibodies for niche targets | Growing |
| Diagnostics | High-specificity binders in lateral flow or ELISA | Moderate |
| Antibody-based delivery | Antibody-drug or antibody-RNA conjugates | Emerging |

**ToxBind: Snake Venom Binder Case Study**   
Snakebite envenoming remains a devastating and neglected tropical disease, claiming over 100,000 lives annually and causing severe complications and long-lasting disabilities for many more. At present, the only available treatments for snakebites consist of polyclonal antibodies derived from the plasma of immunized animals, which have a high cost and limited efficacy against the venoms. Although critical in saving lives, it can cause severe adverse effects; it has been complemented by extra-intense medical and surgical care. These treatments are often ineffective in severe cases. Further, the accessibility is hindered by high production costs. And the fact that it has been stored in cold storage means it is not available to remote places, where snake bites are more common. Considering the above, we conclude that there is a need for alternative therapeutics that are easier, more effective, cheaper, and do not require being stored at a freezing temperature. 

For many decades, scientists have been studying the proteomics of various snake species. A detailed and compiled study suggests that, even though there are more than 3500 species of snakes, only \~500 snake species are venomous enough to kill humans. These snakes belong to three families, namely: Elapidae, Viperidae, and Crotalinae. Further, all venomous species of snakes are front-fanged, except for a few rear-fanged species of the Colubridae family. Snake venoms are mixtures of different protein families, and each of these families contains many other toxins. Upon analyzing the venom of various snakes, it is found that only a few protein families are responsible for significant damage. 

The proteins are Short-chain alpha neurotoxin, Long-chain alpha neurotoxin, and Cytotoxin. Short-chain alpha neurotoxin and long-chain neurotoxin bind to muscle-type nAChRs (nicotinic acetylcholine receptors), disrupting motor movement and making the subject paralyzed. Further, cytotoxin affects the cell by disrupting primary cell functions, leading to its death, which is the cause of tissue necrosis. A detailed analysis and quantification of proteins is covered here. It highlights the commonality between snake venoms, which are fatal to humans. 

There is active research underway to [develop a universal snake antivenom](https://www.centivax.com/portfolio). Additionally, as discussed earlier, recent AI-based methods for generating proteins have demonstrated significant potential in developing novel and functional de novo proteins for various applications. Given that, all proteins, at the molecular level, are made of the same building blocks. So, it presents the opportunity of applying the same methods to tackle this problem as well. 

If successful, such potent, stable, and readily manufacturable toxin-neutralizing proteins could provide the basis for safer, cost-effective, and widely accessible next-generation antivenom therapeutics.

**Indian Biotech Market**   
India’s biotech is fast growing, contributing 4.10% share of the national GDP in 2022\. Over the past decade, India’s bioeconomy has grown significantly, from $10 billion in 2014 to $151 billion by the end of 2023\. And it is expected to reach $300 billion by 2030\. India’s bioeconomy can be classified into four primary sectors: 

1. BioPharma & BioMedical: The sector includes the development of pharmaceuticals, medical devices, diagnostics, and related technologies. It focuses on areas like cancer immunotherapy, gene editing, precision medicine, and biologics.   
2. BioIndustrial: This emerging sector deals with bio-based chemicals and products produced through the use of enzymes, biosynthetic processes, and recombinant DNA technology. It encompasses biofuels, bioplastics, biogas, and enzymatic applications across various industries, including the beverage and detergent sectors.  
3. BioAgri: Focusing on agricultural biotechnology, this subsector covers genetically modified crops, precision agriculture, and bio-based products.  
4. BioServices: This segment involves contract research, clinical trials, biotech software and databases, specialized equipment, and bioscience education services 

The BioIndustrial (48.09% Share, $72.6 Billion) and BioPharma (35.65% Share, $53.8 Billion) sector combined contributes 83.74% of the total bioeconomy. If we look at the above two industries, we will be focused on bioplastics and enzymatic applications. Furthermore, pharmaceuticals and biologics are also part of our plan, either directly or indirectly. However, one thing to highlight here is that, even though these fields make up a big part of the economy, there is still not much emphasis on R\&D, which, in the future, could lead to reliance on other companies. 

India is the leading global vaccine manufacturer, meeting 24% of the total vaccine demand. The global vaccine market remains highly concentrated, with just nine manufacturers accounting for over 70% of the worldwide supply, excluding COVID-19 vaccines. Notably, three of these manufacturers: Serum Institute of India, Bharat Biotech International Ltd, and Biological E Ltd, are based in India, underscoring the country’s significant contribution to global vaccine production. To maintain the lead in the long run, it is essential to invest heavily in research and development. 

India’s biotech startup sector continues its rapid ascent, with the last three years showcasing exponential growth. As of 2023, there are 8,531 startups in the biotech and life sciences. It is also challenging to estimate how many of them are focusing on high-risk research in the field of emerging protein-based therapeutics markets. There are a few exceptions. PopVax, a Hyderabad-based startup, focuses on mRNA-based vaccine research. At the same time, ImmunoACT, based in Mumbai, develops successful therapeutics in cell and gene therapy, all of which are created in India.

From a growth point of view, by 2030, the India BioEconomy is projected to double to $300 billion, up from $151 billion in 2023, reflecting a robust compound annual growth rate (CAGR) of 12.3%. BioIndustrial Projected to reach $121 billion with a steady CAGR of 7.5% while BioMedical is expected to grow at a CAGR of 13.2%, reaching $128 billion by 2030\. 

The global BioEconomy will continue to grow rapidly in the upcoming decade. Currently, Italy and Spain lead the way with 22% of GDP. Thanks to their early focus on basic research. India and China’s bioeconomies are at the same level of 4%. The rise of AI methods will significantly shape the next wave of the economy. 

Much of our work is based on open-source software, and we plan to open-source the tool, allowing everyone to use it and thereby accelerating research and development in the field of protein engineering. 

If this mission also excites you, please reach out at [hi@hemeai.com](mailto:hi@hemeai.com)

Thanks  
Satish 


[^1]:  Currently, more than 50+ [companies](https://harrisbio.notion.site/) are focusing on different aspects. 

[^2]: If we get lucky;  Here, Hit refers to a protein (antibody, enzymes, or binders)

[^3]:  Here, language implies a protein sequence made up of a string of amino acids
