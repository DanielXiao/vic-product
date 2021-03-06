#Default Volume Store Error

When you create or run a container, the Docker operation fails with an error about a missing volume store.  

##Problem
Running the container fails with error:

	docker: Error response from daemon: No volume store named (default) exists.

## Cause

By default, vic-machine create does not create a volume store when the vSphere administrator deploys a VCH. To run containers from images that use volumes, the vSphere administrator must specify a volume store named default when they deploy the VCH.

## Solution

Deploy a VCH by using the `vic-machine create --volume-store` option to create a VCH with a volume store named `default`. See  [Specify Volume Stores](../vic_vsphere_admin/volume_stores.md).

Use `docker volume inspect` to get information about the volume. 