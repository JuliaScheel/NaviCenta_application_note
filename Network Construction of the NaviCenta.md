
# Network Construction of the NaviCenta

This document serves as a brief introduction into network construction for Disease Maps for NaviCenta ([NaviCenta](https://www.sbi.uni-rostock.de/minerva/index.xhtml?id=NaviCenta)) users. This is followed by a summary of networks currently included in the NaviCenta and a short referenced statement of why (if at all) they are placenta specific.

## Challenge and Solution

In contrast to “simple” diseases, “complex” diseases have a multifactorial cause by a combination of lifestyle, genetic, and genetic factors, affecting various pathways, cell types as well as tissues. Nonlinear interactions between cells and their associated pathways often leave the prediction of outcome non-intuitive [1]. These parts of a complex disease are constructed in individual submaps and later merged into the actual Disease Map (DM).

In brief, a DM is a comprehensive model and intuitive visualization of cellular and molecular mechanisms specific to organ, tissue, and the disease of interest that can be translated into a computational model. It presents a knowledge repository by providing information about the regulatory relationships between biochemical entities, such as genes, proteins, small molecules, and ions. DMs are also used as a first step towards advanced network analyses and potential drug target identification [2], [3].

## Introduction to Network Construction:

Biological network construction for DMs is done using languages that facilitate both human and machine readability and interpretation. Examples are Systems Biology Markup Language (SBML), Biological Pathway Exchange (BioPAX), CellML, NeuroML, Synthetic Biology Open language (SBOL), Simulation Experiment Description Markup Language (SED-ML), and Systems Biology Graphical Notation (SBGN) [4].

DM networks can be constructed as process descriptions (PD) and activity flows (AF). PD is used to describe detailed mechanisms of biomolecular interactions, while AF describes the flow of information between elements in a graph. DMs often use both representations, however usually not within the same submap. The styles use the same species-specific glyphs but different reaction types [5] (Figure 1).

![](media/be73911a7a4ac0305afe7be2a38490ad.jpg)

Figure 1: Comparison of activity flow, process description, and the combination of both. The approaches differ not only visually but also in their usability. PD includes mechanistic processes between elements, leading to a high information low readability model. The high information content ensures high reusability. Activity Flow diagrams visualize the flow of information, creating more concise visual representations, at the cost of information integration. The combined approach has the highest readability to information content ratio, but has lower reusability. Most analysis methods and tools are specific to PD or AF and cannot be applied to combined approach models. The schema was inspired by Kondratova et al. [6].

## Network Construction for the NaviCenta:

The NaviCenta was created using CellDesigner [7]. To adequately capture mechanisms of importance, the NaviCenta was constructed in multiple interconnected parts and layers, curated by experts and published on the publicly available platform Minerva [8].

The NaviCenta consists of three functional layers (Figure 2A) [9]. The top-layer describes higher-level processes involved in healthy and dysfunctional placentation, visualizing tissue level organization, cellular processes and clinically important phenotypes.

The basis for modularization and choice of networks was a literature review that was started with key publications suggested by domain experts within the iPlacenta consortium.

The process layer contains activity flow and process description diagrams of key molecular pathways depicted in the top-layer previously identified. These included accepted biomarkers for PE and IUGR seed molecules as a basis (<https://github.com/JuliaScheel/NaviCenta_application_note/tree/main/Known%20Disease-Related%20Molecules>).

The Molecular Interaction Map (MIM) contains signal flow diagrams and are enriched with regulatory components i.e. TF, miRNA, lncRNA and drug interaction data (Figure 2B) [10]. .![](media/84de5839cbf67bd5585599eff76f4d24.jpg)

Figure 2: Functional layers of disease maps. (A) The top-layer is often a description of the disease context, visualizing tissue level organization and cellular processes and phenotypes of importance. This layer is mainly used by clinicians to visualize Fluorescence-activated cell sorting (FACS) data, support patient stratification and clinical decision making. The process layer contains activity flow and process description diagrams containing key molecules and pathways depicted in the disease context top-laye. It serves as a tool for coordination and modularization and is used by experimentalists for hypothesis making and omics data visualization. The MIM contains al signal flow diagrams and are enriched with i.e. TF, miRNA, lncRNA and drug interaction data. This layer is used by bioinformaticians for the identification of molecular switches, loops, regulatory motifs, and possible drug targets. Disease maps are generated using a top-down, bottom-up, or combined (“middle-out”) approach (B). In the top-down approach databases and articles are scanned to identify relevant processes and phenotypes. In The bottom-up approach, known disease-related molecules are used as seed molecules for network construction and expansion. Activity flow diagrams describing the molecular pathways behind each identified process are then integrated with the networks generated in the top-down approach and can be extended with overlays resulting in a deep molecular level network. TF, transcription factors.

## Overview of NaviCenta Networks

Table 1: Overview of NaviCenta networks: This table lists all included networks and indicates the newly created submaps, as well as which ones have been adapted from other existing disease maps, and which existing models have been included, including the respective publication and a very simplified description of their placenta specific content.

| **Network**                                | **Newly created**  | **Adapted from other disease map** | **Other included models** | **Publication** | **Placenta specific**                                                                                                                                                              |
|--------------------------------------------|--------------------|------------------------------------|---------------------------|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Angiogenesis                               | x                  |                                    | R-HSA-194138 R-HSA-194313 | [11]            | This network was created based on original data and integrated into relevant interaction networks based on placenta specific articles                                              |
| B cell                                     |                    | AIR                                |                           | [3]             |                                                                                                                                                                                    |
| Haemostasis                                |                    | AIR                                |                           | [3]             |                                                                                                                                                                                    |
| Mast Cell Signalling                       |                    | AIR                                |                           | [3]             |                                                                                                                                                                                    |
| M1                                         |                    | AIR                                |                           | [3]             | Placental macrophages display specific phenotypesl Maps were therefore adjusted [12]                                                                                               |
| M2                                         |                    | AIR                                |                           | [3]             | Placental macrophages display specific phenotypes. Maps were therefore adjusted [12]                                                                                               |
| Macrophage M1 M2 switch                    | x                  |                                    |                           |                 |                                                                                                                                                                                    |
| Mitochondria                               | x                  |                                    | R-HSA-71403 WP5241        | [13]            |                                                                                                                                                                                    |
| Mitochondrial Dysfunction                  | x                  |                                    |                           | [13]            | Mitochondrial dysfunction is associated with placental dysfunction and therefore constructed as a network                                                                          |
| Monocyte transmigration                    |                    | AIR                                |                           | [3]             |                                                                                                                                                                                    |
| NK Cell Chemotaxis                         |                    | AIR                                |                           | [3]             |                                                                                                                                                                                    |
| Neutrophil apoptosis                       |                    | AIR                                |                           | [3]             |                                                                                                                                                                                    |
| Neutrophil chemotaxis                      |                    | AIR                                |                           | [3]             |                                                                                                                                                                                    |
| Redox Pathway                              | x                  |                                    | [14]–[27]                 | [28]            | Redox Signalling Pathways have been associated with placental dysfunction. This network was created based on existing models and extended based on placenta specific publications. |
| Th22 cell                                  |                    | AIR                                |                           | [3]             | Th22 cells have been shown to interact with throphoblast cells, which is included in the network [29]                                                                              |
| Th1                                        |                    |                                    |                           | [3]             | Th1 have been shown to interact with syncytiotrophoblast and extravillous cytotrophoblast cells [30]                                                                               |
| Th17                                       | x                  |                                    |                           |                 |                                                                                                                                                                                    |
| Th2                                        |                    | AIR                                |                           | [3]             | Th2 cells have been shown to interact with trophoblast cells [30]                                                                                                                  |
| Treg                                       | x                  |                                    |                           |                 |                                                                                                                                                                                    |
| Trophoblast differentiation                | x                  |                                    |                           |                 | In itself placenta specific                                                                                                                                                        |
| Vasodilation vasoconstriction permeability |                    | AIR                                |                           | [3]             |                                                                                                                                                                                    |
| Cell adhesion                              | x                  |                                    |                           |                 |                                                                                                                                                                                    |
| Complement                                 | x                  |                                    |                           |                 |                                                                                                                                                                                    |
| Cytotoxic T cell                           | x                  |                                    |                           |                 |                                                                                                                                                                                    |
| Endothelial Dysfunction                    | x                  |                                    | R-HSA-203615              | [13]            | Placental dysfunctions have been associated with an interplay between trophoblast cells and endothelial dysfunction as indicated in this network                                   |
| Hofbauer Cells                             | x                  |                                    |                           |                 | Hofbauer cells are placental villous macrophages [31]                                                                                                                              |
| Non Apoptotic Cell Death                   | x                  |                                    | WP4313                    |                 |                                                                                                                                                                                    |
| uNK                                        | x                  |                                    |                           |                 | Uterine NKs are adapted for their function and environment [32]                                                                                                                    |

## Outlook

The scientific outlook for Navicenta with respect to placental research encompasses a multifaceted approach aimed at unraveling the complexities of the placenta. Fundamental to this pursuit is the more thorough investigation of trophoblast cell interactions, which will further enrich the NaviCenta. Simultaneously, there is a recognized need to bolster research efforts dedicated to the placenta in general [33], [34]. By integrating disease mechanisms, including already included conditions like PE and IUGR, and expanding the scope to encompass other placental dysfunctions, we were able to develop a more comprehensive understanding of the spectrum of placental-related complications. Vital to this progression is the identification and validation of biomarkers, enabling early diagnosis and monitoring of these conditions. Collaborative endeavors and the integration of the NaviCenta into other online resources like the previous Placental Atlas Tool [35] will play an integral role in facilitating knowledge exchange and fostering advancements in placental research. Lastly, investment in translational research opens avenues for innovative therapeutic strategies to address placenta-related complications. Collectively, these endeavors will broaden our understanding of poorly studied placental dysfunctions and ultimately pave the way for improved maternal and fetal health outcomes.

**References**

[1] D. J. Hunter, “Gene-environment interactions in human diseases,” *Nature Reviews Genetics*, vol. 6, no. 4. Nature Publishing Group, pp. 287–298, Apr-2005.

[2] A. Mazein *et al.*, “Systems medicine disease maps: community-driven comprehensive representation of disease mechanisms,” *npj Syst. Biol. Appl.*, vol. 4, no. 1, pp. 1–10, Dec. 2018.

[3] C. N. Serhan *et al.*, “The Atlas of Inflammation-Resolution (AIR),” *bioRxiv*, p. 2020.01.27.921882, Feb. 2020.

[4] F. Schreiber *et al.*, “Specifications of Standards in Systems and Synthetic Biology: Status and Developments in 2017,” *J. Integr. Bioinform.*, vol. 15, no. 1, Mar. 2018.

[5] V. Touré, N. Le Novère, D. Waltemath, and O. Wolkenhauer, “Quick tips for creating effective and impactful biological pathways using the Systems Biology Graphical Notation,” *PLOS Comput. Biol.*, vol. 14, no. 2, p. e1005740, Feb. 2018.

[6] M. Kondratova, N. Sompairac, E. Barillot, A. Zinovyev, and I. Kuperstein, “Signalling maps in cancer research: Construction and data analysis,” *Database*, vol. 2018, no. 2018, p. 36, Jan. 2018.

[7] A. Funahashi, Y. Matsuoka, A. Jouraku, M. Morohashi, N. Kikuchi, and H. Kitano, “CellDesigner 3.5: A versatile modeling tool for biochemical networks,” *Proc. IEEE*, vol. 96, no. 8, pp. 1254–1265, 2008.

[8] D. Hoksza, P. Gawron, M. Ostaszewski, J. Hasenauer, and R. Schneider, “Closing the gap between formats for storing layout information in systems biology,” *Brief. Bioinform.*, vol. 21, no. 4, pp. 1249–1260, Jul. 2020.

[9] M. Ostaszewski *et al.*, “COVID19 Disease Map, a computational knowledge repository of virus-host interaction mechanisms,” *Mol. Syst. Biol.*, vol. 17, no. 10, Oct. 2021.

[10] D. Hoksza, P. Gawron, M. Ostaszewski, E. Smula, R. Schneider, and L. Cowen, “MINERVA API and plugins: Opening molecular network analysis and visualization to the community,” *Bioinformatics*, vol. 35, no. 21, pp. 4496–4498, Nov. 2019.

[11] N. Gebara *et al.*, “Single extracellular vesicle analysis in human amniotic fluid shows evidence of phenotype alterations in preeclampsia,” *bioRxiv*, p. 2022.02.14.480331, Feb. 2022.

[12] S. Mezouar, M. Katsogiannou, A. Ben Amara, F. Bretelle, and J. L. Mege, “Placental macrophages: Origin, heterogeneity, function and role in pregnancy-associated infections,” *Placenta*, vol. 103, p. 94, Jan. 2021.

[13] Y. Correia, J. Scheel, S. Gupta, and K. Wang, “Placental mitochondrial function as a driver of angiogenesis and placental dysfunction,” *Biol. Chem.*, vol. 402, no. 8, pp. 887–909, Jul. 2021.

[14] K. Duhig, L. C. Chappell, and A. H. Shennan, “Oxidative stress in pregnancy and reproduction,” *Obstet. Med.*, vol. 9, no. 3, pp. 113–116, Sep. 2016.

[15] R. Orabona *et al.*, “Pre-eclampsia and heart failure: a close relationship,” *Ultrasound Obstet. Gynecol.*, vol. 52, no. 3, pp. 297–301, Sep. 2018.

[16] C. H. Coyle and K. N. Kader, “Mechanisms of H2O2-induced oxidative stress in endothelial cells exposed to physiologic shear stress,” *ASAIO J.*, vol. 53, no. 1, pp. 17–22, Jan. 2007.

[17] L. Padayachee, J. M. Rohwer, and C. S. Pillay, “The thioredoxin redox potential and redox charge are surrogate measures for flux in the thioredoxin system,” *Arch. Biochem. Biophys.*, vol. 680, p. 108231, Feb. 2020.

[18] A. M. Guimera, D. P. Shanley, and C. J. Proctor, “Modelling the role of redox-related mechanisms in musculoskeletal ageing,” *Free Radic. Biol. Med.*, vol. 132, pp. 11–18, Feb. 2019.

[19] K. T. Kasawara, S. L. Do Nascimento, M. L. Costa, F. G. Surita, and J. L. P. E Silva, “Exercise and physical activity in the prevention of pre-eclampsia: systematic review,” *Acta Obstet. Gynecol. Scand.*, vol. 91, no. 10, pp. 1147–1157, Oct. 2012.

[20] C. Espinosa-Diez *et al.*, “Antioxidant responses and cellular adjustments to oxidative stress,” *Redox Biol.*, vol. 6, pp. 183–197, Dec. 2015.

[21] Y. Zhang, Y. Deng, X. Yang, H. Xue, and Y. Lang, “The Relationship Between Protein S-Nitrosylation and Human Diseases: A Review,” *Neurochem. Res.*, vol. 45, no. 12, pp. 2815–2827, Dec. 2020.

[22] K. Toboła-Wróbel, M. Pietryga, P. Dydowicz, M. Napierała, J. Brązert, and E. Florek, “Association of Oxidative Stress on Pregnancy,” *Oxid. Med. Cell. Longev.*, vol. 2020, 2020.

[23] H. Hughes, C. V. Smith, E. C. Horning, and J. R. Mitchell, “High-performance liquid chromatography and gas chromatography-mass spectrometry determination of specific lipid peroxidation products in vivo,” *Anal. Biochem.*, vol. 130, no. 2, pp. 431–436, Apr. 1983.

[24] A. M. W. Penn *et al.*, “MELAS syndrome with mitochondrial tRNA(Leu)(UUR) mutation: correlation of clinical state, nerve conduction, and muscle 31P magnetic resonance spectroscopy during treatment with nicotinamide and riboflavin,” *Neurology*, vol. 42, no. 11, pp. 2147–2152, 1992.

[25] D. Graham *et al.*, “Mitochondria-targeted antioxidant MitoQ10 improves endothelial function and attenuates cardiac hypertrophy,” *Hypertens. (Dallas, Tex. 1979)*, vol. 54, no. 2, pp. 322–328, Aug. 2009.

[26] Y. Iwakiri *et al.*, “Nitric oxide synthase generates nitric oxide locally to regulate compartmentalized protein S-nitrosylation and protein trafficking,” *Proc. Natl. Acad. Sci. U. S. A.*, vol. 103, no. 52, p. 19777, Dec. 2006.

[27] M. Mirabelli, E. Chiefari, V. Tocci, E. Greco, D. Foti, and A. Brunetti, “Gestational diabetes: Implications for fetal growth, intervention timing, and treatment options,” *Curr. Opin. Pharmacol.*, vol. 60, pp. 1–10, Oct. 2021.

[28] S. Manna *et al.*, “Computational Models on Pathological Redox Signalling Driven by Pregnancy: A Review,” *Antioxidants 2022, Vol. 11, Page 585*, vol. 11, no. 3, p. 585, Mar. 2022.

[29] N. Lanir, A. Aharon, and B. Brenner, “Haemostatic mechanisms in human placenta,” *Best Pract. Res. Clin. Haematol.*, vol. 16, no. 2, pp. 183–195, 2003.

[30] F. Liu *et al.*, “Placental trophoblasts shifted Th1/Th2 balance toward Th2 and inhibited Th17 immunity at fetomaternal interface,” *APMIS*, vol. 119, no. 9, pp. 597–604, Sep. 2011.

[31] L. Reyes and T. G. Golos, “Hofbauer cells: Their role in healthy and complicated pregnancy,” *Front. Immunol.*, vol. 9, no. NOV, p. 410754, Nov. 2018.

[32] M. M. Faas and P. de Vos, “Uterine NK cells and macrophages in pregnancy,” *Placenta*, vol. 56, pp. 44–52, Aug. 2017.

[33] S. Matsuzaki *et al.*, “Relationship between Abnormal Placenta and Obstetric Outcomes: A Meta-Analysis,” *Biomedicines*, vol. 11, no. 6, p. 1522, May 2023.

[34] K. L. Thornburg and N. Marshall, “THE PLACENTA IS THE CENTER OF THE CHRONIC DISEASE UNIVERSE,” *Am. J. Obstet. Gynecol.*, vol. 213, no. 4 0, p. S14, Oct. 2015.

[35] J. V. Ilekis *et al.*, “The Placental Atlas Tool (PAT): A collaborative research and discovery platform for the placental research community,” *Placenta*, vol. 80, pp. 42–48, May 2019.
