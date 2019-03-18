<!-- archived-provider -->
This Terraform provider is archived, per our [provider archiving process](https://terraform.io/docs/internals/archiving.html). What does this mean?

1. The code repository and all commit history will still be available.
1. Existing released binaries will remain available on the releases site.
1. Documentation will remain on the Terraform website.
1. Issues and pull requests are not being monitored.
1. New releases will not be published.

If anyone from the community or an interested third party is willing to maintain it, they can either be granted access here or fork the repository for their own uses. If you are interested in maintaining this provider, please reach out to the [Terraform Provider Development Program](https://www.terraform.io/guides/terraform-provider-development-program.html) at *terraform-provider-dev@hashicorp.com*.

---

<!-- /archived-provider -->

**Note:** The SoftLayer provider is deprecated and not under active development. It will not work with many IBM Cloud resources and is not compatible with the new IBM Cloud APIs.

Terraform Provider
==================

- Website: https://www.terraform.io
- [![Gitter chat](https://badges.gitter.im/hashicorp-terraform/Lobby.png)](https://gitter.im/hashicorp-terraform/Lobby)
- Mailing list: [Google Groups](http://groups.google.com/group/terraform-tool)

![Terraform](https://rawgithub.com/hashicorp/terraform/master/website/source/assets/images/logo-hashicorp.svg)

Requirements
------------

-	[Terraform](https://www.terraform.io/downloads.html) 0.10.x
-	[Go](https://golang.org/doc/install) 1.8 (to build the provider plugin)

Building The Provider
---------------------

Clone repository to: `$GOPATH/src/github.com/hashicorp/terraform-provider-$PROVIDER_NAME`

```sh
$ mkdir -p $GOPATH/src/github.com/hashicorp; cd $GOPATH/src/github.com/hashicorp
$ git clone git@github.com:hashicorp/terraform-provider-$PROVIDER_NAME
```

Enter the provider directory and build the provider

```sh
$ cd $GOPATH/src/github.com/hashicorp/terraform-provider-$PROVIDER_NAME
$ make build
```

Using the provider
----------------------
## Fill in for each provider

Developing the Provider
---------------------------

If you wish to work on the provider, you'll first need [Go](http://www.golang.org) installed on your machine (version 1.8+ is *required*). You'll also need to correctly setup a [GOPATH](http://golang.org/doc/code.html#GOPATH), as well as adding `$GOPATH/bin` to your `$PATH`.

To compile the provider, run `make build`. This will build the provider and put the provider binary in the `$GOPATH/bin` directory.

```sh
$ make bin
...
$ $GOPATH/bin/terraform-provider-$PROVIDER_NAME
...
```

In order to test the provider, you can simply run `make test`.

```sh
$ make test
```

In order to run the full suite of Acceptance tests, run `make testacc`.

*Note:* Acceptance tests create real resources, and often cost money to run.

```sh
$ make testacc
```
