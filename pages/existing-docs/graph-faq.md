---
title: "FAQ"
excerpt: ""
---
[block:callout]
{
  "type": "info",
  "body": "On this page, you'll find the most common questions regarding the Seven Bridges graph-based whole genome sequencing analysis app (Graph WGS).\n\nIf your question is not in this FAQ section, feel free to contact us at team@sbgenomics.com."
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "On this page:",
  "body": "* [What is Graph WGS?](doc:graph-faq#section-what-is-graph-wgs-)\n* [What is graph technology?](doc:graph-faq#section-what-is-graph-technology-)\n* [How is the graph reference genome built?](doc:graph-faq#section-how-is-the-graph-reference-genome-built-)\n* [How does Graph WGS perform the analysis?](doc:graph-faq#section-how-does-graph-wgs-perform-the-analysis-)\n* [What kind of variants can Graph WGS identify?](doc:graph-faq#section-what-kind-of-variants-can-graph-wgs-identify-)\n* [Will Graph WGS work for analysing datasets other than whole genome sequencing data](doc:graph-faq#section-will-graph-wgs-work-for-analysing-datasets-other-than-whole-genome-sequencing-data-)\n* [What reference genome can I use with Graph WGS?](doc:graph-faq#section-what-reference-genome-can-i-use-with-graph-wgs-)\n* [What file formats does Graph WGS accept?](doc:graph-faq#section-what-file-formats-does-graph-wgs-accept-)\n* [Do I have to pay to use Graph WGS?](doc:graph-faq#section-do-i-have-to-pay-to-use-graph-wgs-)\n* [How long will it take Graph WGS to complete?](doc:graph-faq#section-how-long-will-it-take-graph-wgs-to-complete-)\n* [How do I get Graph WGS?](graph-faq#section-how-do-i-get-graph-wgs-)\n* [How can I run Graph WGS on the Seven Bridges Platform using the Google Cloud Platform infrastructure?](doc:graph-faq#section-how-can-i-run-graph-wgs-on-the-seven-bridges-platform-using-the-google-cloud-platform-infrastructure-)\n* [How can I troubleshoot a failed task running Graph WGS?](doc:graph-faq#section-how-can-i-troubleshoot-a-failed-task-running-graph-wgs-)\n* [How do I access my Graph WGS task logs?](doc:graph-faq#section-how-do-i-access-my-graph-wgs-task-logs-)\n* [How can I add Graph WGS to my workflow?](graph-faq#section-how-can-i-add-graph-wgs-to-my-workflow-)\n* [How can I access the CWL JSON file?](graph-faq#section-how-can-i-access-the-cwl-json-file-)\n* [Can I access the Graph WGS Docker image?](graph-faq#section-can-i-access-the-graph-wgs-docker-image-)\n* [Can I edit Graph WGS in the Workflow Editor?](graph-faq#section-can-i-edit-graph-wgs-in-the-workflow-editor-)\n* [How do I get the output files?](graph-faq#section-how-do-i-get-the-output-files-)"
}
[/block]
###What is Graph WGS?

Graph WGS is the Seven Bridges **Graph**-based **W**hole **G**enome **S**equencing Analysis app.

<div align="right"><a href="#top">top</a></div>

###What is graph technology?

In the context of genomics, graph technology refers to using a graph structure to store and analyse variations between genomes, in contrast to the traditional linear approach.
A linear reference genome is built from a small number of individuals and is therefore not an accurate description of genetic variants within a population. This leads to inaccurate read alignment against that reference, which in turn biases the discovery of new genetic variants. This reference bias can be addressed by using a graph structure to achieve a more accurate description of genetic variation within a population. Work with small genomic regions containing high sequence or structural diversity has shown that using a graph reference produces [better read alignment and improved variant calling](http://www.nature.com/ng/journal/v47/n6/full/ng.3257.html). Seven Bridges’s Graph WGS app makes graph technology applicable at the whole genome level, enabling powerful and highly accurate read alignment and variant calling.

<div align="right"><a href="#top">top</a></div>

###How is the graph reference genome built?

The graph reference genome is built using genomes from a wide range of human populations, including data from the [1000 Genomes Project](http://www.1000genomes.org) and the [Simons Genome Diversity Project Datasets](https://www.simonsfoundation.org/life-sciences/simons-genome-diversity-project-dataset/). The differences between genomes are stored for every position in the genome using a directed acyclic graph. Given that human genomes are 99.9% identical, the increase in storage requirements is minimal with the addition of a new genome to the population reference graph, allowing analysis to be carried out at a previously impossible scale.

<div align="right"><a href="#top">top</a></div>

###How does Graph WGS perform the analysis?

Sequencing reads are aligned to the reference graph in a two-step process. First, regions to which a read is likely to map to in the graph are identified using a fast global search algorithm. In the second step, the read is aligned against the graph reference genome, using a precise local alignment algorithm. Following the alignment step, a Bayesian variant caller is used to detect variants from the aligned reads.

<div align="right"><a href="#top">top</a></div>

###What kind of variants can Graph WGS identify?

Unlike linear alignment methods that treat all genetic variants as novel, graph aligner incorporates known variants to get more precise alignments and gives us more accurate detection of known and novel variants.
The use of graph technology, enables you not only to detect complex variants, but also cases when a complex variant is phased with a SNP. This allows you to find multiple interconnected/correlated mutation events in the genome.
Unlike any of the current linear alignment methods, graph aligner can also detect variants within variants due to the implementation of variation graphs.

<div align="right"><a href="#top">top</a></div>

###Will Graph WGS work for analysing datasets other than whole genome sequencing data?

Yes, as long as your input [contains the required read type, file format, and metadata]
(doc:manual-inputs), you can input similar types of data e.g. whole human exome sequencing data. However, bear in mind that Graph WGS has been optimised for whole genome sequencing analysis, and its strength lies in the ability to identify the traditionally elusive long structural variations, and variations in highly repetitive genomic regions.

<div align="right"><a href="#top">top</a></div>

###What reference genome can I use with Graph WGS?

You can choose between the human genome reference builds v37 and v38 when defining your app settings for your Graph WGS draft task. Seven Bridges have built graph reference genomes corresponding to HGv37 and HGv38, using available variant information. Graph reference genome build v37 is recommended as it contains better variant characterisation. There are few public variant datasets built on top of v38.

<div align="right"><a href="#top">top</a></div>

###What file formats does Graph WGS accept?

Graph WGS accepts any of the following input formats: FQ, FASTQ, FQ.GZ, FASTQ.GZ. Read more about [input file requirements](doc:graph-genome-app-overview#section-inputs).

<div align="right"><a href="#top">top</a></div>

###Do I have to pay to use Graph WGS?

When you run Graph WGS on the Seven Bridges Platform, you will be [charged per execution](doc:payments). For example, performing a whole genome sequencing analysis using two high quality paired-end raw FASTQ files (~80 GB) – similar to the task described in the [Graph WGS tutorial](doc:graph-tutorial) – will cost you about $14.10.

<div align="right"><a href="#top">top</a></div>

###How long will it take Graph WGS to complete?

Running one whole genome sequencing analysis using high-quality raw FASTQ (~80 GB), like the one described in the [Graph WGS tutorial](doc:graph-tutorial), will take you about 8 hours. The exact time will depend on the compression of your FASTQ inputs.

<div align="right"><a href="#top">top</a></div>

###How do I get Graph WGS?

Graph WGS is available by request to Seven Bridges Platform users running Amazon Web Services cloud infrastructure. [Learn how to be one of the first people to use Graph WGS](doc:graph-genome-app-overview#section-accessing-graph-wgs).

<div align="right"><a href="#top">top</a></div>

###How can I run Graph WGS on the Seven Bridges Platform using the Google Cloud Platform infrastructure?

If you are using the Seven Bridges Platform with the Google Cloud Platform infrastructure (https://gcp.sbgenomics.com/), please get in touch with us at support@sbgenomics.com to get access to Graph WGS.

<div align="right"><a href="#top">top</a></div>

###How can I troubleshoot a failed task running Graph WGS?

If your task running Graph WGS fails, the error is immediately analysed and you will shortly be contacted by one of the Seven Bridges bioinformaticians with advice on how to get the task up and running.

<div align="right"><a href="#top">top</a></div>

###How do I access my Graph WGS task logs?

As a Graph WGS user, you do not have access to the Graph WGS task logs. However, if your task does fail, one of the Seven Bridges bioinformaticians will be in touch to help with troubleshooting.

<div align="right"><a href="#top">top</a></div>

###How can I add Graph WGS to my workflow?

Graph WGS is a standalone app and cannot be connected to other tools or workflows using the Workflow Editor.

<div align="right"><a href="#top">top</a></div>

###How can I access the CWL JSON file?

As a Graph WGS user, you do not have access to the Common Workflow Language (CWL) JSON file for the app. If you request the CWL JSON for Graph WGS via the API, a limited number of fields will be returned.

<div align="right"><a href="#top">top</a></div>

###Can I access the Graph WGS Docker image?

Users don't have access the Graph WGS Docker image.

<div align="right"><a href="#top">top</a></div>

###Can I edit Graph WGS in the Workflow Editor?

Users cannot edit the Graph WGS app or see any of its components.

<div align="right"><a href="#top">top</a></div>

###How do I get the output files?

Once your Graph WGS task has finished running, you can [view and download the output files](doc:graph-tutorial#section-get-your-results).

<div align="right"><a href="#top">top</a></div>