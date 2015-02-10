cooker v1.0
===========

Cooker is a tool to be used on top of packer.io ( http://github.com/outscale/packer ), which provides a way a build a set of appliances and OS images on the Outscale IaaS infrastructure ( it also works with Amazon AWS )

Install
-------

Just copy the cooker script at the root of this repos to a suitable place ( say a directory listed in $PATH like /usr/local/bin/ )

```shell
cp cooker /usr/local/bin
```

Usage
-----

In order to use cooker, you will need your Outscale ( or Amazon) Access and Secret Keys.

Once you have these information, you can initialize cooker with the following command:

```shell
cooker init <YOUR_AK> <YOUR_SK> <REGION>
```

This step will then automatically fetch the last version of the recipes on github and prepare your cooker environment.

* To List available images to be built:

```shell
cooker list
```

This command will return you a list of path-like image identifiers, to be used when wanting to build an image.

* To build an image:

```shell
cooker cook <image_identifier>
```

At the end of this command and if the build process went fine, the command will return you the AMI-id of the image.

Note: image_identifier is the one of the lines returned by the "cooker list" command.

