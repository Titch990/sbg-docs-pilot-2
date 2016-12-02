---
title: "QuickStart"
excerpt: "<a name=\"top\"></a>To introduce you to the major features of the Seven Bridges Platform, this QuickStart will walk you through the process of a simple whole exome sequencing analysis.\n\n<a href=\"#tldr\">...in a nutshell</a>"
---

<!-- Adding to check this link works -->
<div align="right"><a href="#tldr">in a nutshell . . . </a></div>

## Prerequisites
All the resources used in the QuickStart, including the files and workflow, are available to you when you <a href="https://www.sbgenomics.com/login" target="blank">sign up for a free account</a>: there is no need to take out a subscription — just use some of your free $100 credits.

[block:callout]
{
  "type": "info",
  "body": "We encourage you to follow these steps and to try the analysis for yourself. This is the easiest way to become familiar with the Seven Bridges Platform!",
  "title": "Try it out yourself!"
}
[/block]

## Procedure
We'll start by creating a project and populating it with FASTQ files. Then, we'll use one of the Seven Bridges whole exome analysis workflows to carry out the analysis. Finally, we'll examine our results.

[block:callout]
{
  "type": "warning",
  "title": "On this page:",
  "body": "* [Create a project](#section-create-a-project)\n* [Enter file metadata](#section-enter-file-metadata)\n* [Add FASTQ files to your project](#section-add-fastq-files-to-your-project)\n* [Select a public workflow ](#section-select-a-public-workflow)\n* [Edit the selected workflow](#section-edit-the-selected-workflow)\n* [Run the analysis](#section-run-the-analysis)\n* [View the results](#section-view-the-results-of-the-data-analysis)"
}
[/block]

## Create a project
The first step to running an analysis on the Seven Bridges Platform is to create a project. To do this, click **Create a project** under the **Projects** tab in the top navigation bar. 

This will open a new window where you can name your project and select a [billing group](doc:payments). Let's name our project **QuickStart**. We'll use the free **Pilot Funds** as our billing group. When you're finished, click **Create**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/vhHeGIWATCqKeFJvJTsw_q1.jpg",
        "q1.jpg",
        "483",
        "406",
        "#d7992c",
        ""
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "success",
  "title": "Project URL",
  "body": "Your project is given a URL based on its name. While you can rename your project at any point in time, the URL cannot be altered after your project has been created."
}
[/block]

Once you create a project, you'll be taken to its [Project Dashboard](doc:project-dashboard). This page contains all the information about your project, including its files, apps (tools and workflows), tasks (workflow executions), and project members.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/gReuWS6rQb6htcHcujeY_quickstart2.jpg",
        "quickstart2.jpg",
        "1413",
        "784",
        "#74acdc",
        ""
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Learn more about adding project members and specifying their level of access in the documentation on [managing project members](doc:collaboration).",
  "title": "Manage project members"
}
[/block]

<div align="right"><a href="#top">top</a></div>

## Add FASTQ files to your project

The next step is to add the FASTQ files to your project. The other reference files needed for the analysis will be suggested when you set up the workflow.

To find the FASTQ files necessary for the analysis, click the **Files** tab on your project dashboard and then **+Add files**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/QwJehTD0Q0GkTilFTpd0_quickstart3.jpg",
        "quickstart3.jpg",
        "704",
        "374",
        "#528b5c",
        ""
      ],
      "border": true
    }
  ]
}
[/block]

Clicking **+Add files** opens the file browser. Here you can view the Public Reference Files repository, **Public Files** and any files that you've already added to other projects.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/11cc623-quickstart-add-files_1.jpg",
        "quickstart-add-files_1.jpg",
        1243,
        799,
        "#f4f4f5"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "There are several ways to add files to the Platform; you can add them from a [computer](doc:copy-files-using-the-visual-interface) or via [FTP/HTTP](doc:copy-files-using-the-api)."
}
[/block]

For this analysis, we want to use two paired-end files that contain whole exome sequencing data. We'll select **Public Files** on the sidebar and use the search box to quickly locate them.

Since we want to find a pair of FASTQ files named **C835.HCC1143.2.converted.pe_1.fastq** and **C835.HCC1143.2.converted.pe_2.fastq**, we'll enter "C835.HCC1143.2.converted.pe" into the search box to find them.

If you don't know the names of the files you need, you can instead browse all files. Learn more about [searching for files ](doc:search-files-on-the-platform) on the Seven Bridges Platform.

Select both files using the checkboxes adjacent to the filenames, as shown below. To copy the files, click **Copy to Project** and confirm. To return to the Project Dashboard, just close the **File** window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a69ac99-quickstart-add-files_2.jpg",
        "quickstart-add-files_2.jpg",
        1225,
        720,
        "#eef1f2"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "success",
  "body": "Copy multiple files at once by checking all files before clicking **Copy to Project**"
}
[/block]

<div align="right"><a href="#top">top</a></div>

## Enter file metadata
It is important to annotate your files with [Metadata on the Seven Bridges Platform](doc:metadata-on-the-seven-bridges-platform) when you perform an analysis on the Platform so that bioinformatics tools processing files in parallel can group files with identical metadata value(s) in specified fields.

File metadata includes information about the File (e.g. experimental strategy and library ID), **Sample** (e.g. sample ID), and **General** (e.g. investigation and species) . For more information on the metadata fields used on the Platform, please see the documentation on [file metadata](metadata-on-the-seven-bridges-platform).

Click the **Files** tab on your project dashboard to see all the files in the project. Currently our project, QuickStart, only contains the two files that we've just added.

To edit a file's metadata, select the file and click **Edit Metadata**. You can add (the same) metadata for both files at once. Or, you can do add metadata individually if your files have different metadata. We can edit the metadata for both of the FASTQ files simultaneously.

Select both of the files and click **Edit Metadata**. This will open a pop-up window with inputs for the different metadata fields. Notice the empty field for Platform unit ID. This needs to be set to run the task. Enter 1 in this field, and click **Save**.

This metadata will inform tools that these files come from the same sample, were produced by the same library, and have been sequenced on the same lane.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a9ff35a-quickstart-edit-metadata-1.jpg",
        "quickstart-edit-metadata-1.jpg",
        1364,
        790,
        "#4b4945"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Each file used in an analysis on the Seven Bridges Platform must have their own metadata values. For more information, see the [metadata documentation](doc:metadata-on-the-seven-bridges-platform) on grouping and distinguishing files by metadata.\n\nIn the example here, note that while we have set the same **Library ID**, **Platform unit ID**, and **Platform** values for the two WES_human_Illumina files, the two files come with different **Paired-end** values ('1' and '2') by default."
}
[/block]

<div align="right"><a href="#top">top</a></div>

## Select a public workflow 

The next step is selecting a public workflow for running the analysis. We'll use the workflow, **Whole Exome Sequencing GATK 2.3.9.-lite**, which is based on the free version of the GATK tool developed by the Broad Institute.

This workflow is one of Seven Bridges' many open source workflows available to all users on the Platform. These workflows have been tested to run efficiently in the cloud environment by the Seven Bridges bioinformatics team.

To select a public workflow for use in your project, navigate to **Apps** tab on your project dashboard and click **+Add App**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e4dVYTatQamX2LfFXPyJ_quickstart5.jpg",
        "quickstart5.jpg",
        "774",
        "422",
        "#6a8495",
        ""
      ],
      "border": true
    }
  ]
}
[/block]

To add the Whole Exome Sequencing workflow:

1. Type 'whole exome' into the search box. The Whole Exome Sequencing GATK 2.3.9.-lite will be displayed in the search results.

![image in step](https://files.readme.io/faaa5b0-add-workflow-layout-1.jpg)

<!--[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/faaa5b0-add-workflow-layout-1.jpg",
        "add-workflow-layout-1.jpg",
        1066,
        734,
        "#367bb8"
      ],
      "border": true
    }
  ]
}
[/block]-->

2. Next, click **Copy **below the workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3e75eeb-add-workflow-layout-2.jpg",
        "add-workflow-layout-2.jpg",
        1067,
        720,
        "#f3f4f4"
      ],
      "border": true
    }
  ]
}
[/block]

3. (Optional) Set the name of the workflow in your project.
4. Click **Copy** and the workflow will be added to your project.

To go back to the project dashboard, close the app browser window.

<div align="right"><a href="#top">top</a></div>

## Edit the selected workflow
In many cases, you might want to tweak a workflow to work better with your dataset. This can be done easily using the workflow editor. To edit your workflow in your project, navigate to the **Apps** tab and click the pencil icon next to **Whole Exome Analysis - BWA + GATK 2.3.9-lite**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/DrlhSPGnSZOW3bU8jYfl_qq4.jpg",
        "qq4.jpg",
        "1356",
        "597",
        "#477454",
        ""
      ],
      "border": true
    }
  ]
}
[/block]

This opens the workflow editor containing a graphical representation of the workflow where each tool, input, and reference file is represented as a node. To see a description of the workflow's function and other details such as toolkit name and version, tool author, and its license, you can click Additional Information.

To the right of the workflow diagram, the panel labeled **APPS** displays a list of all the apps available in your projects (**MyApps**) or among **PublicApps**.

The **PARAMS** panel describes the parameters of the tools used in this workflow and allows you to make quick edits.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2vu2DhmQAiqAJJpaeb18_quickstart11.jpg",
        "quickstart11.jpg",
        "1637",
        "806",
        "#3a698e",
        ""
      ],
      "border": true
    }
  ]
}
[/block]

On the workflow editor, click the **BWA-MEM Bundle** node (see the screenshot below). This opens the **PARAMS** tab, which displays the parameters of **BWA-MEM Bundle** sorted into **Input/Output options**, **Scoring options**, **Execution**, etc. Let's find the parameter **use_soft_clipping **and select it.

This will soft clip the supplementary alignments. To save this change as a new revision of the workflow, click **Save**. Note that clicking **Save** changes the version number from 0 to 1. This function allows you to keep track all your workflow edits.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/mGOWNvImR2O585SmdFJL_quickstart12.jpg",
        "quickstart12.jpg",
        "1423",
        "750",
        "#54ab6d",
        ""
      ],
      "border": true
    }
  ]
}
[/block]

<div align="right"><a href="#top">top</a></div>

## Run the analysis
Now that the workflow is ready, it's time to run the analysis. We'll click **Run**, in the upper right corner. The pop-up window with the suggested files for this workflow will be displayed.

[block:callout]
{
  "type": "info",
  "body": "For all public workflows on the Seven Bridges Platform our team of bioinformaticians has chosen a set of recommended input files."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/35859bd-copy-suggested-files.png",
        "copy-suggested-files.png",
        1130,
        641,
        "#b4b4b4"
      ],
      "border": true
    }
  ]
}
[/block]

Click **Copy** and the suggested files will be copied to your project and added as input files to our workflow. The files are mapped the following way.

[block:parameters]
{
  "data": {
    "h-0": "Input port",
    "h-1": "Input files",
    "0-0": "Known_SNPs\n\nKnown_Indels",
    "0-1": "dbsnp_137.b37.vcf\n\nMills_and_1000G_gold_standard.indels.b37.sites.vcf\n1000G_phase1.indels.b37.vcf",
    "1-0": "Target_BED",
    "1-1": "exome_targets.b37.bed",
    "2-0": "SnpEff_Database",
    "2-1": "snpEff_v3_6_GRCh37.75.zip",
    "4-0": "Reference or TAR with BWA reference indices",
    "4-1": "human_g1k_v37_decoy.fasta",
    "3-0": "FASTQ",
    "3-1": "C835.HCC1143.2.converted.pe_1.fastq\nC835.HCC1143.2.converted.pe_2.fastq",
    "h-2": "File type",
    "0-2": "**VCF** files contain databases of the known genetic variants - SNPs and indels.",
    "1-2": "**BED** files contain all target regions which are relevant for our analysis - in this case exomes. It points to the relevant locations of the FASTA file we are using for the analysis.",
    "2-2": "**ZIP file (snpEff) **is a specific build of the snpEff database which contains annotations of the genetic variants and their supposed effects.",
    "3-2": "**FASTQ** files contain the experiment data for our analysis i.e. they are the output of the high-throughput sequencing instruments; for the purpose of the QuickStart guide, we will use a pair of FASTQ files which represent one whole exome sample from the TCGA dataset",
    "4-2": "**FASTA** file is a reference genome which we will use for the alignment of the FASTQ files."
  },
  "cols": 3,
  "rows": 5
}
[/block]

On the **DRAFT Task page** you will see two tabs: **Set Input Data** and **Define App Settings**, as shown in the screenshot below. The second tab shows various tool parameters that we've exposed by unlocking them in the workflow editor.

We'll ignore these for now (for details, see the documentation on [tool settings](doc:the-tool-editor). The tab marked **Set Input Data** is where you can enter the input files and reference files for your workflow.

<!-- This is how to encode a basic image, assuming it's in my project. It isn't yet, so this won't work! -->
![Picking FASTQ files](/images/picking-fastq.png)

<!-- . . .  so this is the actual imagelocation from the [block] below. This should work! -->
![Picking FASTQ files](https://files.readme.io/79db182-picking-fastq.png)

<!-- original encoding of image -->
  
<!-- [block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/79db182-picking-fastq.png",
        "picking-fastq.png",
        914,
        907,
        "#eff0f1"
      ],
      "border": true
    }
  ]
}
[/block]-->

The only remaining files you need to select are FASTQ files. Click **Pick file(s)** and choose these files:
**  * C835.HCC1143.2.converted.pe_1.fastq
**  * C835.HCC1143.2.converted.pe_2.fastq**

After adding the two FASTQ files, we can start this execution by clicking **Run**.

When you start the task, a new page opens displaying the task's properties. To see all the tasks that have run or are running in this project, click **Back to tasks** in the upper left corner.

Here you can see the name of each task, the project member who started it, its initiation time, the execution workflow, its status, and available task actions.

The status will be a progress bar if the task is still running or a label notifying whether the task has completed, been aborted or failed. Additional information, including how to check the status of the task or how to troubleshoot in case of the failed task, is available in the documentation on [task statistics](doc:view-task-stats).

<div align="right"><a href="#top">top</a></div>

## View the results of the data analysis
Once the task is completed, you'll be notified via email. The easiest way to access results is to go to the **Tasks** tab. This shows all the information related to this particular execution.

On the **Tasks** page, the column marked **Outputs** shows the results produced by the tools in the executed workflow. In our example task, take a look at **summary_metrics** report. Clicking on the file name opens the alignment metrics from the task.

At the bottom of the screen you can see the task's raw output.

The result of the data analysis is shown in the **raw VCF file**. The raw VCF contains all the variants detected by the workflow. To download it, just click on its filename. This will open a new page displaying the contents of the file and some information describing it. Then click **Download** in the upper right corner.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cf2c9b5-workflow-output-files.png",
        "workflow-output-files.png",
        1280,
        771,
        "#d4d6d8"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "success",
  "body": "Note that the names of files outputted from a tool incorporate part of the tool's name. This makes it easier to find report files from a list of outputs."
}
[/block]

That’s it! We've executed a data analysis and obtained some results. We encourage you to try this procedure for yourself before getting started on your own data analyses. You can also visit the rest of our [Knowledge Center](http://docs.sevenbridges.com/v1.0) to learn more about the Seven Bridges Platform and bringing your own tools.

<div align="right"><a href="#top">top</a></div>

<hr><a name="tldr"></a>

### In a nutshell
* **Create a project** to hold your analyses on the Seven Bridges Platform.
* **Add files** to your project and supply their metadata to prepare them for analyses. Don't forget to add reference files!
* **Add and edit a public workflow** (Whole Exome Analysis - BWA + GATK 2.3.9-Lite) to run your whole exome sequencing analysis.
* **Set up your task** on the **DRAFT** task page by selecting inputs and reference files.
* The **Outputs** page displays the results of your task.

<hr>
<div align="right"><a href="http://docs.sevenbridges.com/docs/sign-up">Next: <i>See our documentation in full: start from learning to sign up for the Platform <b>>></b></i></a></div>

**Suggested pages:**

[Troubleshoot a failed task](doc:troubleshoot-a-failed-task) 
[API Quickstart](doc:api-quickstart) 
[Seven Bridges Platform tutorials](doc:seven-bridges-platform-tutorials)