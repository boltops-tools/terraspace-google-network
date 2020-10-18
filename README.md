# Terraspace Google Network Example

This project shows how to use the [Network Terraform registry module ](https://registry.terraform.io/modules/terraform-google-modules/network/google) with [Terraspace](https://terraspace.cloud/).

* Thanks and credit goes to the author of this module: Eric J.
* Most contributors are doing this on their own free time. Please support them. Contribute back and send them a pull request. Some may ask for donations. Donate to them. Some are consultants. Hire them.

## Setup

    git clone https://github.com/boltops-tools/terraspace-google-network
    cd terraspace-google-network
    bundle

## Deploy

Make sure the `GOOGLE_PROJECT` env variable is set your google project. One easy way to set it:

    export GOOGLE_PROJECT=`gcloud config get-value project`

Then to deploy:

    terraspace up simple_project

The network named `demo-dev-network` is created.

If you want to change the tfvars variables change at:

    app/stacks/simple_project/tfvars/dev.tfvars

## Updating

To update the modules to the latest version from the Terraform registry.

    rm -rf app/stacks
    terraspace bundle update

Then create a tfvars file with these contents:

app/stacks/simple_project/tfvars/dev.tfvars:

    project_id   = "<%= ENV['GOOGLE_PROJECT'] %>"
    network_name = "demo-dev-network"

## More Examples

    $ terraspace list
    app/stacks/delete_default_gateway_routes
    app/stacks/ilb_routing
    app/stacks/multi_vpc
    app/stacks/secondary_ranges
    app/stacks/simple_project
    app/stacks/simple_project_with_regional_network
    app/stacks/submodule_firewall
    app/stacks/submodule_network_peering
    app/stacks/submodule_svpc_access

## About

[![BoltOps Badge](https://img.boltops.com/boltops/badges/boltops-badge.png)](https://www.boltops.com)

[Terraspace](https://terraspace.cloud/) and this project was built by [BoltOps](https://www.boltops.com). We also offer:

* [Paid Consulting Services](https://www.boltops.com/consulting)
* [BoltOps Pro: Infrastructure Code as a Service](https://www.boltops.com/pro)
