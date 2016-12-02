---
title: "AWS S3 policy generator"
excerpt: ""
---
This page lets you generate an IAM policy suitable for use with the [Volumes API](doc:volumes-v2), for volumes associated with AWS S3 buckets. 

The policy will grant Seven Bridges read-only or read-write access to one or more AWS S3 buckets. You can use a single policy to configure access to multiple volumes.

To create a policy:
1. Select the environment with which you are using the Volumes API.
2. Enter the bucket or bucket/prefix path for the volume.
3. Select the desired access mode for this volume (read only or read-write).
4. If you are configuring multiple buckets, click <i>+ Add another</i> and redo.
5. When you have finished, click <i>Generate IAM Policy</i>.
[block:embed]
{
  "html": false,
  "url": "https://custom-doc-html.sbgenomics.com/iam-user-policy.html",
  "title": null,
  "favicon": null,
  "iframe": true,
  "width": "100%",
  "height": "1000px"
}
[/block]