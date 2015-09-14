# docker-list-patches
docker subcommand to list available patches

This and idea for the Docker Global Hack Day #3

Inspired by "zypper-docker":

https://github.com/SUSE/zypper-docker

Since I am very bad at explaining myself, here an example of what I want to accomplish:
List whether there is an update that contains patches

  > docker list-patches myimage
  >
  > Available patches:
  >
  > patch #123: Fix bug #456
  >
  > patch #231: Fix bug #333
  >
  > Please update to version xxxx with
  >
  > docker pull myimage:xxx
  
Lists whether your image has an update available that fixes CVE2015XXX

  > docker list-patches --cve=CVE-2015XXX myimage
  >
  > patch#123: fixes CVE-2015XXX 
  >
  > Please update to version xxxx with
  >
  > docker pull myimage:xxx
  


The whole idea is to add metadata into the images on whether they contain patches that fix issues, both security and non-security ones.

Then, when you do a "docker list-patches myimage", docker will download the metadata for new releases of your image and look into that.
