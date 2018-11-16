Openshift Image pulling
=======================

This play pulls in all the images required for running openshift in disconnected environments.


Requirements
===========

It requires ansible 2.7 and podman, with any environment variables for outbound proxy already set. 

Container storage should also be configured to handle the volume, 100G would be sufficient.

Vars
===

    defined_images:

The set of images that cant be extacted from imagestreams and templates that need to mirrored. 
Basically everythiung from the doco, along with any extra images that might be required.
https://docs.openshift.com/container-platform/3.11/install/disconnected_install.html

    image_repos:

openshift-ansible and any other repo that contains templates and image streams can be used.
You can specify a set of files or dirs, it will load all files specified and any json or yaml content
in the directories listed. Then attempt to parse the files for any any referenced images

    repo_images:

This is generated by the openshift-images role based on what was provided in image_repos dictionary.


