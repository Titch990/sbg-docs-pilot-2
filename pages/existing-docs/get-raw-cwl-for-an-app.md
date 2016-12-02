---
title: "Get raw CWL for an app"
excerpt: "/apps/{app_id}/raw\n\nFor general information on the API, including formatting, parameters, and pagination, please see the [API Overview](the-api)."
---
This call returns information about the specified app, as raw CWL. The call differs from the call to [ `GET` details of an app](doc:get-details-of-an-app) by returning a JSON object that is the CWL. 

The app should be one in a project that you can access; this could be an app that has been uploaded to the Seven Bridges Platform by a project member, or a publicly available app that has been copied to the project.
[block:code]
{
  "codes": [
    {
      "code": "https://api.sbgenomics.com/v2/apps/{app_id}/raw",
      "language": "text",
      "name": "Path for Amazon Web Services users"
    },
    {
      "code": "https://gcp-api.sbgenomics.com/v2/apps/{app_id}/raw",
      "language": "text",
      "name": "Path for Google Cloud Platform users"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "success",
  "body": "Recall from the [API Overview](doc:the-api#section-identifying-projects-users-apps-files-tasks-and-inputs) that the `app_id` has the form `{project_owner}/{project}/{app_short_name}/{revision_number}`\n\nNote that if you omit `revision_number`, the API will return the latest app revision.\n\nYou can get the `app_id` for an app by making the call to [list all apps available to you](doc:list-all-apps-available-to-you)",
  "title": "app_ids"
}
[/block]
##Request

###Example request
[block:code]
{
  "codes": [
    {
      "code": "GET /v2/apps/RFranklin/my-project/bamtools-merge-2-4-0/raw HTTP/1.1\nHost: api.sbgenomics.com\nX-SBG-Auth-Token: 3259c50e1ac5426ea8f1273259740f74\n",
      "language": "http",
      "name": null
    },
    {
      "code": "curl  -s -H \"X-SBG-Auth-Token: 6282d5e2121d43e7900e9d52b15845e7\" -H \"content-type: application/json\" -X GET \"https://api.sbgenomics.com/v2/apps/RFranklin/my-project/bamtools-merge-2-4-0/raw\"",
      "language": "curl",
      "name": "cURL"
    }
  ],
  "sidebar": true
}
[/block]
###Header Fields
[block:parameters]
{
  "data": {
    "h-0": "Name",
    "h-1": "Description",
    "0-0": "`X-SBG-Auth-Token`\n_required_",
    "0-1": "Your Seven Bridges Platform [authentication token](doc:get-your-authentication-token).",
    "h-2": ""
  },
  "cols": 2,
  "rows": 1
}
[/block]
###Path parameters
[block:parameters]
{
  "data": {
    "0-0": "`app_id`",
    "h-0": "Name",
    "h-1": "Description",
    "0-1": "The ID for the app you are querying. It can be obtained by making the call to [list all apps available to you](doc:list-all-apps-available-to-you)"
  },
  "cols": 2,
  "rows": 1
}
[/block]
###Query parameters
[block:parameters]
{
  "data": {
    "h-0": "Name",
    "h-1": "Data type",
    "h-2": "Description",
    "0-0": "`fields`",
    "0-1": "string",
    "0-2": "Selector specifying a subset of fields to include in the response."
  },
  "cols": 3,
  "rows": 1
}
[/block]
##Response

[See a list of Seven Bridges Platform-specific response codes that may be contained in the body of the response.](doc:api-status-codes) 

###Example response body
Note that this call returns the full CWL description of the app.
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"successCodes\": [],\n  \"sbg:homepage\": \"https://github.com/pezmaster31/bamtools/wiki\",\n  \"sbg:validationErrors\": [],\n  \"sbg:sbgMaintained\": false,\n  \"temporaryFailCodes\": [],\n  \"requirements\": [],\n  \"sbg:latestRevision\": 0,\n  \"description\": \"BamTools Merge merges multiple BAM files into a single file.\",\n  \"sbg:job\": {\n    \"inputs\": {\n      \"region\": \"chr1\",\n      \"input_bam_files\": [\n        {\n          \"path\": \"1.bam\"\n        },\n        {\n          \"path\": \"2.bam\"\n        }\n      ]\n    },\n    \"allocatedResources\": {\n      \"cpu\": 1,\n      \"mem\": 1000\n    }\n  },\n  \"sbg:toolAuthor\": \"Derek Barnett, Erik Garrison, Gabor Marth, and Michael Stromberg\",\n  \"hints\": [\n    {\n      \"dockerImageId\": \"f808163d4cd3\",\n      \"class\": \"DockerRequirement\",\n      \"dockerPull\": \"images.sbgenomics.com/markop/bamtools:2.4.0\"\n    },\n    {\n      \"value\": 1,\n      \"class\": \"sbg:CPURequirement\"\n    },\n    {\n      \"value\": 1000,\n      \"class\": \"sbg:MemRequirement\"\n    }\n  ],\n  \"sbg:copyOf\": \"djordje_klisic/public-apps-by-seven-bridges/bamtools-merge-2-4-0/0\",\n  \"sbg:createdOn\": 1452181866,\n  \"arguments\": [\n    {\n      \"position\": 1,\n      \"prefix\": \"-out\",\n      \"separate\": true,\n      \"valueFrom\": \"merged.bam\"\n    }\n  ],\n  \"outputs\": [\n    {\n      \"sbg:fileTypes\": \"BAM\",\n      \"id\": \"#output_bam_file\",\n      \"outputBinding\": {\n        \"glob\": \"merged.bam\",\n        \"sbg:metadata\": {},\n        \"sbg:inheritMetadataFrom\": \"#input_bams\"\n      },\n      \"description\": \"Output BAM file.\",\n      \"type\": [\n        \"File\"\n      ],\n      \"label\": \"Output BAM file\"\n    }\n  ],\n  \"sbg:categories\": [\n    \"SAM/BAM-Processing\"\n  ],\n  \"sbg:contributors\": [\n    \"RFranklin\"\n  ],\n  \"sbg:links\": [\n    {\n      \"id\": \"https://github.com/pezmaster31/bamtools\",\n      \"label\": \"Homepage\"\n    },\n    {\n      \"id\": \"https://github.com/pezmaster31/bamtools/wiki\",\n      \"label\": \"Wiki\"\n    }\n  ],\n  \"stdout\": \"\",\n  \"stdin\": \"\",\n  \"sbg:project\": \"RFranklin/my-project\",\n  \"inputs\": [\n    {\n      \"sbg:fileTypes\": \"BAM\",\n      \"id\": \"#input_bam_files\",\n      \"inputBinding\": {\n        \"sbg:cmdInclude\": true,\n        \"prefix\": \"-in\",\n        \"separate\": true,\n        \"itemSeparator\": null,\n        \"position\": 0\n      },\n      \"description\": \"The input BAM files.\",\n      \"label\": \"Input BAM files\",\n      \"type\": [\n        {\n          \"type\": \"array\",\n          \"items\": \"File\"\n        }\n      ],\n      \"sbg:category\": \"Input & Output\"\n    },\n    {\n      \"id\": \"#region\",\n      \"inputBinding\": {\n        \"sbg:cmdInclude\": true,\n        \"position\": 2,\n        \"separate\": true,\n        \"prefix\": \"-region\"\n      },\n      \"description\": \"A region of interest (e.g. \\\"chr1:500..chr3:1500\\\"). See the documentation for more info.\",\n      \"label\": \"Region of interest\",\n      \"type\": [\n        \"null\",\n        \"string\"\n      ],\n      \"sbg:category\": \"Input & Output\"\n    }\n  ],\n  \"label\": \"BamTools Merge\",\n  \"sbg:createdBy\": \"RFranklin\",\n  \"baseCommand\": [\n    \"/opt/bamtools/bin/bamtools\",\n    \"merge\"\n  ],\n  \"sbg:toolkitVersion\": \"2.4.0\",\n  \"sbg:id\": \"RFranklin/my-project/bamtools-merge-2-4-0/0\",\n  \"sbg:license\": \"The MIT License\",\n  \"sbg:revision\": 0,\n  \"sbg:cmdPreview\": \"/opt/bamtools/bin/bamtools merge -in 1.bam -in 2.bam -out merged.bam -region chr1\",\n  \"sbg:modifiedOn\": 1452181866,\n  \"id\": \"https://api.sbgenomics.com/RFranklin/my-project/bamtools-merge-2-4-0/0/raw/\",\n  \"class\": \"CommandLineTool\",\n  \"sbg:modifiedBy\": \"RFranklin\",\n  \"sbg:revisionsInfo\": [\n    {\n      \"sbg:modifiedBy\": \"RFranklin\",\n      \"sbg:modifiedOn\": 1452181866,\n      \"sbg:revision\": 0\n    }\n  ],\n  \"sbg:toolkit\": \"BamTools\"\n}",
      "language": "json"
    }
  ],
  "sidebar": true
}
[/block]