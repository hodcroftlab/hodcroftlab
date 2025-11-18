---
title: Enterovirus D68 now on Nextclade!
image: /assets/images/blog/cover_image_nextclade_blog.png
author: nadia-neuner-jehle
categories: 
    - projects
    - nextclade
    - nextstrain
    - enterovirus
    - ev-d68
layout: post
toc: false
date: 2025-11-17
description: "Checkout the new Nextclade dataset for Enterovirus D68!"
---
# Checkout the new Nextclade dataset for Enterovirus D68!
We’re excited to announce the launch of the **first Nextclade dataset for Enterovirus D68 (EV-D68)** - a major step toward easier, faster, and more consistent enterovirus surveillance.
With EV-D68 cases already rising this season, clinicians and researchers can now use **Nextclade** to rapidly analyze their viral sequences, check sequence quality, identify clades, and compare results to a global phylogenetic tree — all within minutes in your web browser and without specialized software.
Created together with the **European Non-Polio Enterovirus Network (ENPEN)**, this first Enterovirus dataset in Nextclade lays the groundwork for future Enterovirus datasets and coordinated surveillance efforts.

You can explore the new Enterovirus D68 dataset [here](https://clades.nextstrain.org/?dataset-name=enpen/enterovirus/ev-d68)!

This dataset was created by [Nadia Neuner-Jehle](/people/nadia-neuner-jehle/), [Alejandra González-Sánchez](/people/alejandra-gonzalez), and [Emma B. Hodcroft](/people/emma-hodcroft/).

### Dataset details

The EV-D68 dataset is based on curated, high-quality whole genome sequences from public databases. It supports:

- **Clade assignments** (A1–A2, B1–B3, and C)
- **Mutation calling** relative to the reference
- **Quality control (QC)** metrics
- **Gene annotations** across the genome

Using whole-genome data allows reliable clade assignments even when VP1 is missing - something that wasn’t possible with earlier approaches.

**Nextclade runs completely within your browser** - no data is uploaded or sent anywhere, making it a completely private way to examine your sequences.

### How to use the EV-D68 dataset in Nextclade

1. **Add your sequences and run the analysis**
    
    Go to [nextclade.org](http://nextclade.org), choose the **Enterovirus D68** dataset, and either drag and drop your FASTA file or load an example. Click **"Run"** to start the analysis. 
    
    Nextclade will align your sequences, assess quality, and assign clades automatically. 
    All processing happens directly in your **web browser.**
    
    ![nextclade_start](/assets/images/blog/nextclade_start.png)
    
2. **Explore your results**
    
    Once processed, you'll be taken to the **Results** section. Here, you can view sequence names (1), quality control (QC) metrics (2), clade assignments (3), and details such as the number of mutations (4), coverage, and gaps relative to the reference.
    
    ![Nextclade_results.svg](/assets/images/blog/Nextclade_results.svg)
    
    The **"Genetic feature"** panel, located to the right of the screen, displays either the entire genome (when "Nucleotide sequence" is selected, as shown in the image) or a single gene, such as VP1. The colored lines represent mutations relative to the reference sequence. Hovering over the lines provides more details on the mutations. If viewing the whole genome, this is shown in nucleotides; if viewing a single gene, it is shown in amino acids. Grayed-out regions indicate missing data. Even if only partial regions are provided (e.g., 3D-pol), clade assignment can still be accurate.

    <h4>References</h4>

    You can change the reference against which your results are compared using the drop-down menu **“Relative to”** in the top-right corner:

    - _Reference_: The default reference is Fermon, and all sequences are aligned against it.
    - _Parent_: The closest parental node in the tree.
    - _Clade founder:_ The most recent common ancestor of all sequences sharing the same clade (e.g. B3 clade founder), inferred from the dataset.
    - _Static Inferred Ancestor:_ A stable sequence close to the root that we have derived from an inferred ancestral node and that will not change in the future. We provide this as a reference because it is equidistant from all sequences in the tree, and more closely related than Fermon. You can view this sequence [here](https://github.com/enterovirus-phylo/nextclade_d68/blob/master/resources/inferred-root.fasta).
    - _Tree root:_ The dataset root, which may shift slightly between dataset releases.\
    <br>
    <h4>Clade Assignments</h4>

    **Clade assignments** are based on the global diversity of *Enterovirus D68*. 
    Current clades include **A** (A1–A2), **B** (B1–B3), and **C**. 

    Clade A2 is sometimes referred to as clade D; therefore, this dataset uses the designation **"A2/D"**.

    The label **"pre-ABC"** indicates very old basal lineages that are no longer circulating. If your sequence is labeled as "pre-ABC" or "unassigned", it may suggest sequencing or assembly issues rather than a true novel lineage — please check carefully!

    <!-- Two-column block: QC legend + image -->
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; align-items: start; margin-top: 40px;">
    

    <div>

    <p>The color of each row reflects your sequence’s <strong>QC status</strong>: 👉🏻 </p>
    <ul>
    <li><strong>Red:</strong> low quality</li>
    <li><strong>Yellow:</strong> moderate quality</li>
    <li><strong>White:</strong> high-quality sequence</li>
    </ul>

    </div>

    <figure style="margin: 0;">
    <img src="/assets/images/blog/results_types.png"
        alt="Results table with three colors"
        style="width: 100%;">
    </figure>

    </div>

    <!-- Second section: Image left, Text right -->
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 5px; align-items: middle;">
    <figure style="margin: 0;">
        <img src="/assets/images/blog/qc_scores.png" alt="QC scores" style="width: 77%;">
    </figure>

    <div>
        <p>👈🏻 You can check which QC metric triggered a warning.  For example, a red <strong>“P”</strong> indicates an unusually high number of private mutations, and the   <strong>“F”</strong> is highlighted because the frame shift is not expected.</p>
        <p>See the <a href="https://docs.nextstrain.org/projects/nextclade/en/latest/user/nextclade-web/analysis-results-table.html">Nextclade guide</a> for more details on QC metrics and result interpretation.</p>
    </div>
    </div>

    <br>

3. **View your sequences in the phylogenetic tree**
    
    In the **Tree** view (button on the top-left), your sequences appear within the global reference phylogeny. By default, the sequence you provided will be shown as larger circles, and the branches they are connected to, by larger lines (1). The sequences in the reference dataset appear as the thinner lines (2). To view both your sequences and the reference tree together, toggle the 👁️ ‘eye’ icon (hide) at the top left of the tree (3), or remove the filter altogether with the 🗑️ ‘trash’ icon (remove).
    
    Just as on a Nextstrain tree, you can color branches by metadata such as "QC status" or "Clade" (4). Some color schemes, such as Country, will apply only to the reference tree. You can also apply other filters to the data, or view the tree in different formats (such as radial view).
    
    ![Nextclade_tree.svg](/assets/images/blog/Nextclade_tree.svg)
    
    The reference tree provides a curated, down-sampled view of global *EV-D68* diversity and we aim to update it at least once a year to reflect new data.
    

4. **Learn more about the dataset**
    
    Clicking **"Dataset"** at the top leads to a detailed description of the its scope. This description includes important information about the current version of the dataset, which could be useful for recreating analyses. The description includes the reference sequence, dataset maintainers, dataset history, features, subgenogroup/clade definitions, reference types, and links to GitHub, documentation, and contact details.
    
5. **Export and share your results**
    
    Use **"Export"** to download alignments, results tables, and phylogenetic trees in various formats such as CSV/TSV/JSON files containing mutation and clade information, as well as tree and annotation files. These files are ideal for sharing or further analysis.
    

### Looking ahead

Work is already underway to expand Nextclade to other Enteroviruses, including **EV-A71**, **CVA10**, and **CVA16**.

Some features we hope to include in the future are:

- **A recombination QC flag** to identify likely recombinant genomes
- **Gene-specific clade assignments** (e.g., for VP1 and 3D)

These additions will further enhance the ability to quickly and easily obtain clade assignments and quality control information about more Enteroviruses.

While Nextclade provides a fast and accessible overview, it is not a replacement for full phylo genetic analyses. To conduct in-depth evolutionary and recombination studies, explore our **Nextstrain Enterovirus trees** at [nextstrain.org/groups/hodcroftlab](https://nextstrain.org/groups/hodcroftlab), which include VP1, whole-genome, and tanglegram views. Or - check out the [Nextstrain tutorial](https://docs.nextstrain.org/en/latest/tutorials/creating-a-phylogenetic-workflow.html) to start setting up your own local build!

We encourage clinicians, researchers, and surveillance teams to explore the new EV-D68 dataset and share their feedback on [GitHub](https://github.com/enterovirus-phylo/nextclade_d68/issues) or via [email](mailto:eve-group@swisstph.ch). Your input helps improve these tools and supports coordinated Enterovirus surveillance worldwide.

If you use this dataset in a publication, please cite [Neuner-Jehle & Hodcroft (2025)](https://doi.org/10.5281/zenodo.17642339) and [Aksamentov et al. (2021)](https://doi.org/10.21105/joss.03773). Citing this work helps us demonstrate its impact and secure resources for continued maintenance!

**Links**:

- 🔗 [EV-D68 Nextclade dataset](https://clades.nextstrain.org/?dataset-name=enpen/enterovirus/ev-d68)
- 🔗 [Nextclade documentation](https://docs.nextstrain.org/projects/nextclade/en/latest/index.html)
- 🔗 [ENPEN website](https://escv.eu/european-non-polio-enterovirus-network-enpen/)
- 🔗 [Dataset Source Code on GitHub](https://github.com/enterovirus-phylo/nextclade_d68)
