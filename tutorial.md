---
layout: tutorial_hands_on

title: 'From reads to (pseudo) counts : guided step by step exploration'
zenodo_link: https://doi.org/10.5281/zenodo.10652085
questions:
- Which biological questions are addressed by the tutorial?
- Which bioinformatics techniques are important to know for this type of data?
objectives:
- The learning objectives are the goals of the tutorial
- They will be informed by your audience and will communicate to them and to yourself
  what you should focus on during the course
- They are single sentences describing what a learner should be able to do once they
  have completed the tutorial
- You can use Bloom's Taxonomy to write effective learning objectives
time_estimation: 3H
key_points:
- The take-home messages
- They will appear at the end of the tutorial
contributors:
- contributor1
- contributor2

---


# Introduction

<!-- This is a comment. -->

General introduction about the topic and then an introduction of the
tutorial (the questions and the objectives). It is nice also to have a
scheme to sum up the pipeline used during the tutorial. The idea is to
give to trainees insight into the content of the tutorial and the (theoretical
and technical) key concepts they will learn.

You may want to cite some publications; this can be done by adding citations to the
bibliography file (`tutorial.bib` file next to your `tutorial.md` file). These citations
must be in bibtex format. If you have the DOI for the paper you wish to cite, you can
get the corresponding bibtex entry using [doi2bib.org](https://doi2bib.org).

With the example you will find in the `tutorial.bib` file, you can add a citation to
this article here in your tutorial like this:
{% raw %} `{% cite Batut2018 %}`{% endraw %}.
This will be rendered like this: {% cite Batut2018 %}, and links to a
[bibliography section](#bibliography) which will automatically be created at the end of the
tutorial.


**Please follow our
[tutorial to learn how to fill the Markdown]({{ site.baseurl }}/topics/contributing/tutorials/create-new-tutorial-content/tutorial.html)**

> <agenda-title></agenda-title>
>
> In this tutorial, we will cover:
>
> 1. TOC
> {:toc}
>
{: .agenda}

# Title for your first section

Give some background about what the trainees will be doing in the section.
Remember that many people reading your materials will likely be novices,
so make sure to explain all the relevant concepts.

## Title for a subsection
Section and subsection titles will be displayed in the tutorial index on the left side of
the page, so try to make them informative and concise!

# Hands-on Sections
Below are a series of hand-on boxes, one for each tool in your workflow file.
Often you may wish to combine several boxes into one or make other adjustments such
as breaking the tutorial into sections, we encourage you to make such changes as you
see fit, this is just a starting point :)

Anywhere you find the word "***TODO***", there is something that needs to be changed
depending on the specifics of your tutorial.

have fun!

## Get data

> <hands-on-title> Data Upload </hands-on-title>
>
> 1. Create a new history for this tutorial
> 2. Import the files from [Zenodo]({{ page.zenodo_link }}) or from
>    the shared data library (`GTN - Material` -> `{{ page.topic_name }}`
>     -> `{{ page.title }}`):
>
>    ```
>    
>    ```
>    ***TODO***: *Add the files by the ones on Zenodo here (if not added)*
>
>    ***TODO***: *Remove the useless files (if added)*
>
>    {% snippet faqs/galaxy/datasets_import_via_link.md %}
>
>    {% snippet faqs/galaxy/datasets_import_from_data_library.md %}
>
> 3. Rename the datasets
> 4. Check that the datatype
>
>    {% snippet faqs/galaxy/datasets_change_datatype.md datatype="datatypes" %}
>
> 5. Add to each database a tag corresponding to ...
>
>    {% snippet faqs/galaxy/datasets_add_tag.md %}
>
{: .hands_on}

# Title of the section usually corresponding to a big step in the analysis

It comes first a description of the step: some background and some theory.
Some image can be added there to support the theory explanation:

![Alternative text](../../images/image_name "Legend of the image")

The idea is to keep the theory description before quite simple to focus more on the practical part.

***TODO***: *Consider adding a detail box to expand the theory*

> <details-title> More details about the theory </details-title>
>
> But to describe more details, it is possible to use the detail boxes which are expandable
>
{: .details}

A big step can have several subsections or sub steps:


## Sub-step with **FastQC**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [FastQC](toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.74+galaxy0) %} with the following parameters:
>    - {% icon param-file %} *"Raw read data from your current history"*: `output` (Input dataset)
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **Trimmomatic**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [Trimmomatic](toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.1) %} with the following parameters:
>    - *"Single-end or paired-end reads?"*: `Single-end`
>        - {% icon param-file %} *"Input FASTQ file"*: `output` (Input dataset)
>    - *"Perform initial ILLUMINACLIP step?"*: `Yes`
>    - In *"Trimmomatic Operation"*:
>        - {% icon param-repeat %} *"Insert Trimmomatic Operation"*
>            - *"Select Trimmomatic operation to perform"*: `Sliding window trimming (SLIDINGWINDOW)`
>        - {% icon param-repeat %} *"Insert Trimmomatic Operation"*
>            - *"Select Trimmomatic operation to perform"*: `Drop reads with average quality lower than a specified level (AVGQUAL)`
>                - *"Minimum average quality required to keep a read"*: `25`
>        - {% icon param-repeat %} *"Insert Trimmomatic Operation"*
>            - *"Select Trimmomatic operation to perform"*: `Drop reads below a specified length (MINLEN)`
>                - *"Minimum length of reads to be kept"*: `50`
>    - *"Output trimmomatic log messages?"*: `Yes`
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **FastQC**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [FastQC](toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.74+galaxy0) %} with the following parameters:
>    - {% icon param-file %} *"Raw read data from your current history"*: `fastq_out` (output of **Trimmomatic** {% icon tool %})
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **Filter with SortMeRNA**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [Filter with SortMeRNA](toolshed.g2.bx.psu.edu/repos/rnateam/sortmerna/bg_sortmerna/2.1b.6) %} with the following parameters:
>    - *"Sequencing type"*: `Reads are not paired`
>        - {% icon param-file %} *"Querying sequences"*: `fastq_out` (output of **Trimmomatic** {% icon tool %})
>    - *"Databases to query"*: `Databases from your history`
>        - {% icon param-files %} *"rRNA databases"*: `output` (Input dataset), `output` (Input dataset), `output` (Input dataset), `output` (Input dataset), `output` (Input dataset), `output` (Input dataset), `output` (Input dataset)
>    - *"Include aligned reads in FASTA/FASTQ format?"*: `Yes (--fastx)`
>        - *"Include rejected reads file?"*: `Yes`
>    - *"Generate statistics file"*: `Yes`
>    - *"Alignment report"*: `Do not report alignments`
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **MultiQC**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [MultiQC](toolshed.g2.bx.psu.edu/repos/iuc/multiqc/multiqc/1.11+galaxy0) %} with the following parameters:
>    - In *"Results"*:
>        - {% icon param-repeat %} *"Insert Results"*
>            - *"Which tool was used generate logs?"*: `FastQC`
>                - In *"FastQC output"*:
>                    - {% icon param-repeat %} *"Insert FastQC output"*
>                        - {% icon param-file %} *"FastQC output"*: `text_file` (output of **FastQC** {% icon tool %})
>        - {% icon param-repeat %} *"Insert Results"*
>            - *"Which tool was used generate logs?"*: `FastQC`
>                - In *"FastQC output"*:
>                    - {% icon param-repeat %} *"Insert FastQC output"*
>                        - {% icon param-file %} *"FastQC output"*: `text_file` (output of **FastQC** {% icon tool %})
>    - *"Report title"*: `RAw data VS Cleaned data`
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **Trinity**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [Trinity](toolshed.g2.bx.psu.edu/repos/iuc/trinity/trinity/2.15.1+galaxy1) %} with the following parameters:
>    - *"Are you pooling sequence datasets?"*: `Yes`
>        - *"Paired or Single-end data?"*: `Single-end`
>            - {% icon param-file %} *"Single-end reads"*: `output_other` (output of **Filter with SortMeRNA** {% icon tool %})
>            - *"Strand specific data"*: `No`
>    - In *"Additional Options"*:
>        - *"Use the genome guided mode?"*: `No`
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **HISAT2**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [HISAT2](toolshed.g2.bx.psu.edu/repos/iuc/hisat2/hisat2/2.2.1+galaxy1) %} with the following parameters:
>    - *"Source for the reference genome"*: `Use a genome from history`
>        - {% icon param-file %} *"Select the reference genome"*: `output` (Input dataset)
>    - *"Is this a single or paired library"*: `Single-end`
>        - {% icon param-file %} *"FASTA/Q file"*: `output_other` (output of **Filter with SortMeRNA** {% icon tool %})
>    - In *"Summary Options"*:
>        - *"Output alignment summary in a more machine-friendly style."*: `Yes`
>        - *"Print alignment summary to a file."*: `Yes`
>    - In *"Advanced Options"*:
>        - *"Input options"*: `Use default values`
>        - *"Alignment options"*: `Use default values`
>        - *"Scoring options"*: `Use default values`
>        - *"Spliced alignment options"*: `Use default values`
>        - *"Reporting options"*: `Use default values`
>        - *"Output options"*: `Use default values`
>        - *"SAM options"*: `Use default values`
>        - *"Other options"*: `Use default values`
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **FastQC**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [FastQC](toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.74+galaxy0) %} with the following parameters:
>    - {% icon param-file %} *"Raw read data from your current history"*: `output_other` (output of **Filter with SortMeRNA** {% icon tool %})
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **Salmon quant**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [Salmon quant](toolshed.g2.bx.psu.edu/repos/bgruening/salmon/salmon/1.10.1+galaxy0) %} with the following parameters:
>    - *"Select salmon quantification mode:"*: `Reads`
>        - *"Select a reference transcriptome from your history or use a built-in index?"*: `Use one from the history`
>            - In *"Salmon index"*:
>                - {% icon param-file %} *"Reference genome"*: `output` (Input dataset)
>        - In *"Data input"*:
>            - *"Is this library mate-paired?"*: `Single-end`
>                - {% icon param-file %} *"FASTQ/FASTA file"*: `output_other` (output of **Filter with SortMeRNA** {% icon tool %})
>                - *"Specify the strandedness of the reads"*: `Infer automatically (A)`
>    - {% icon param-file %} *"File containing a mapping of transcripts to genes"*: `output` (Input dataset)
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **StringTie**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [StringTie](toolshed.g2.bx.psu.edu/repos/iuc/stringtie/stringtie/2.1.1) %} with the following parameters:
>    - {% icon param-file %} *"Input mapped reads"*: `output_alignments` (output of **HISAT2** {% icon tool %})
>    - *"Use a reference file to guide assembly?"*: `Use reference GTF/GFF3`
>        - *"Reference file"*: `Use a file from history`
>            - {% icon param-file %} *"GTF/GFF3 dataset to guide assembly"*: `output` (Input dataset)
>        - *"Output files for differential expression?"*: `DESeq2/edgeR/limma-voom`
>    - In *"Advanced Options"*:
>        - *"Output gene abundance estimation file?"*: `Yes`
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **featureCounts**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [featureCounts](toolshed.g2.bx.psu.edu/repos/iuc/featurecounts/featurecounts/2.0.3+galaxy2) %} with the following parameters:
>    - {% icon param-file %} *"Alignment file"*: `output_alignments` (output of **HISAT2** {% icon tool %})
>    - *"Gene annotation file"*: `A GFF/GTF file in your history`
>        - {% icon param-file %} *"Gene annotation file"*: `output` (Input dataset)
>    - *"Does the input have read pairs?"*: `No, single-end.`
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **Cut**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [Cut](Cut1) %} with the following parameters:
>    - *"Cut columns"*: `c1,c5`
>    - {% icon param-file %} *"From"*: `output_gene_quant` (output of **Salmon quant** {% icon tool %})
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **Filter**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [Filter](Filter1) %} with the following parameters:
>    - {% icon param-file %} *"Filter"*: `output_short` (output of **featureCounts** {% icon tool %})
>    - *"With following condition"*: `c2>=10`
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **Filter**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [Filter](Filter1) %} with the following parameters:
>    - {% icon param-file %} *"Filter"*: `out_file1` (output of **Cut** {% icon tool %})
>    - *"With following condition"*: `c2>=10`
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}

## Sub-step with **Join**

> <hands-on-title> Task description </hands-on-title>
>
> 1. {% tool [Join](toolshed.g2.bx.psu.edu/repos/bgruening/text_processing/tp_easyjoin_tool/1.1.2) %} with the following parameters:
>    - {% icon param-file %} *"1st file"*: `out_file1` (output of **Filter** {% icon tool %})
>    - *"Column to use from 1st file"*: `c1`
>    - {% icon param-file %} *"2nd File"*: `out_file1` (output of **Filter** {% icon tool %})
>    - *"Column to use from 2nd file"*: `c1`
>    - *"Value to put in unpaired (empty) fields"*: `NA`
>
>    ***TODO***: *Check parameter descriptions*
>
>    ***TODO***: *Consider adding a comment or tip box*
>
>    > <comment-title> short description </comment-title>
>    >
>    > A comment about the tool or something else. This box can also be in the main text
>    {: .comment}
>
{: .hands_on}

***TODO***: *Consider adding a question to test the learners understanding of the previous exercise*

> <question-title></question-title>
>
> 1. Question1?
> 2. Question2?
>
> > <solution-title></solution-title>
> >
> > 1. Answer for question1
> > 2. Answer for question2
> >
> {: .solution}
>
{: .question}


## Re-arrange

To create the template, each step of the workflow had its own subsection.

***TODO***: *Re-arrange the generated subsections into sections or other subsections.
Consider merging some hands-on boxes to have a meaningful flow of the analyses*

# Conclusion

Sum up the tutorial and the key takeaways here. We encourage adding an overview image of the
pipeline used.