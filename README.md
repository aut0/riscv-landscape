[![Netlify Status](https://api.netlify.com/api/v1/badges/91337728-8166-4c8f-bc39-9159bf97dcbc/deploy-status)](https://app.netlify.com/sites/landscape/deploys)

# RISC-V Ecosystem Landscape

![RISC-V Logo](https://landscape.riscv.org/images/left-logo.svg)

- [RISC-V Ecosystem Landscape](#riscv-landscape)
  * [Current Version](#current-version)
  * [Interactive Version](#interactive-version)
  * [New Entries](#new-entries)
  * [Logos](#logos)
  * [Proper SVGs](#proper-svgs)
  * [Corrections](#corrections)
  * [External Data](#external-data)
  * [Best Practices Badge](#best-practices-badge)
  * [Non-Updated Items](#non-updated-items)
  * [License](#license)
  * [Formats](#formats)
  * [Installation](#installation)
  * [Vulnerability reporting](#vulnerability-reporting)
  * [Adjusting the Landscape View](#adjusting-the-landscape-view)

This landscape is intended as a map to explore the Ecosystem supported by RISC-V. It is modelled after the Cloud Native Computing Foundation (CNCF) [landscape](https://landscape.cncf.io) and based on the same open source code.

## Current Version

[![RISC-V Ecosystem Landscape](https://landscape.riscv.org/images/landscape.png)](https://landscape.riscv.org/images/landscape.png)

## Interactive Version

Please see [landscape.riscv.org](https://landscape.riscv.org/).

## New Entries

* We are unlikely to create a new category for projects as we'd rather find the best home with the current options.
* Your project or company needs a logo and the logo needs to include the name.
* Crunchbase organization should be the company or organization that controls the software. That is normally the owner of the trademark, whether or not a trademark has been formally filed.

If you think your project should be included, please open a issue to add it to [landscape.yml](https://github.com/riscv-admin/riscv-landscape/issues/new/choose). Ensure to add all required data in the request. For the logo, you can either upload an SVG to the `hosted_logos` directory or put a URL as the value, and it will be fetched. Pull Requests are welcome.

Netlify will generate a staging server for you to preview your updates. Please check that the logo and information appear correctly and then add `LGTM` to the pull request confirming your review and requesting a merge.

### Testing Locally Using Containers

Before you get startedm, ensure you have [Docker](https://docs.docker.com/engine/install/) (or [Podman](https://podman.io/getting-started/installation)) installed. Here we are using Docker. 

#### Clone the source code of RISC-V Landscape

```
$ git clone https://github.com/riscv-admin/riscv-landscape.git
$ cd ./riscv-riscv-landscape
```

#### Build and access your local RISC-V Landscape version

```
$ make run-server-on-docker
# you can also run it directly
$ docker run -ti --rm -p 8001:8001 riscv/landscape
```

As the build progress, if everything is working, a message like the following will be shown:

```
Development server running at http://127.0.0.1:8001/
Starting a new build...
2023-01-17T20:06:20.606Z build result: success
open the latest Landscape build in your browser
http://127.0.0.1:8001/
```

Then you can access it via you web browser, accessing http://127.0.0.1:8001/.

## Logos

The following rules will produce the most readable and attractive logos:

1. We require SVGs, as they are smaller, display correctly at any scale, and work on all modern browsers. If you only have the logo in another vector format (like AI or EPS), please open an issue and we'll convert it to an SVG for you, or you can often do it yourself at https://cloudconvert.com/. Note that you may need to zip your file to attach it to a GitHub issue. Please note that we require pure SVGs and will reject SVGs that contain embedded PNGs since they have the same problems of being bigger and not scaling seamlessly. We also require that SVGs convert fonts to outlines so that they will render correctly whether or not a font is installed. See [Proper SVGs](#proper-svgs) below.
1. When multiple variants exist, use stacked (not horizontal) logos.
1. Don't use reversed logos (i.e., with a non-white, non-transparent background color). If you only have a reversed logo, create an issue with it attached and we'll produce a non-reversed version for you.
1. Logos must include the company, product or project name in English. It's fine to also include words from another language. If you don't have a version of your logo with the name in it, please open an issue and we'll create one for you (and please specify the font).
1. Match the item name to the English words in the logos. So an Acme Rocket logo that shows "Rocket" should have product name "Rocket", while if the logo shows "Acme Rocket", the product name should be "Acme Rocket". Otherwise, logos looks out of place when you sort alphabetically.
1. Google images is often the best way to find a good version of the logo (but ensure it's the up-to-date version). Search for [grpc logo filetype:svg](https://www.google.com/search?q=grpc+logo&tbs=ift:svg,imgo:1&tbm=isch) but substitute your project or product name for grpc.
1. You can either upload an SVG to the `hosted_logos` directory or put a URL as the value, and it will be fetched.

## Proper SVGs

SVGs need to not rely on external fonts so that they will render correctly in any web browser, whether or not the correct fonts are installed. If you have the original AI file, here are the steps in Illustrator to create a proper SVG:

1. Open file in Illustrator
1. Select all text
1. With the text selected, go to Object > Expand in the top menu
1. Export file by going to File > Export > Export As in top menu
1. Select SVG from the format drop down and make sure that "Use Artboards" is checked
1. This will open a SVG options box, make sure to set Decimal to 5 (that is the highest possible, so to ensure that sufficient detail is preserved)
1. Click Okay to export

## Corrections

Please open a pull request with edits to [landscape.yml](landscape.yml). The file [processed_landscape.yml](processed_landscape.yml) is generated and so should never be edited directly.

If the error is with data from [Crunchbase](https://www.crunchbase.com/) you should open an account there and edit the data. If you don't like a project description, edit it in GitHub. If your project isn't showing the license correctly, you may need to paste the unmodified text of the license into a LICENSE file at the root of your project in GitHub, in order for GitHub to serve the license information correctly.

## External Data

The canonical source for all data is [landscape.yml](landscape.yml). Once a day, we download data for projects and companies from the following sources:

* Project info from GitHub
* Funding info from [Crunchbase](https://www.crunchbase.com/)
* Market cap data from Yahoo Finance
* CII Best Practices Badge [data](https://bestpractices.coreinfrastructure.org/)

The update server enhances the source data with the fetched data and saves the result in [processed_landscape.yml](processed_landscape.yml). The app loads a JSON representation of processed_landscape.yml to display data.

## Best Practices Badge

As explained at https://bestpractices.coreinfrastructure.org/:
>The Linux Foundation (LF) Core Infrastructure Initiative (CII) Best Practices badge is a way for Free/Libre and Open Source Software (FLOSS) projects to show that they follow best practices. Projects can voluntarily self-certify, at no cost, by using this web application to explain how they follow each best practice. The CII Best Practices Badge is inspired by the many badges available to projects on GitHub. Consumers of the badge can quickly assess which FLOSS projects are following best practices and as a result are more likely to produce higher-quality secure software.

The interactive landscape displays the status (or non-existence) of a badge for each open-source project. There's also a feature not available through the filter bar to see all items [with](https://landscape.graphql.org/bestpractices=yes) and [without](https://landscape.graphql.org/bestpractices=no) badges. Note that a passing badge is a requirement for projects to [graduate](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc) in the CNCF.

## Non-Updated Items

We generally remove open source projects that have not had a commit in over 3 months. Note that for projects not hosted on GitHub, we need them to mirror to GitHub to fetch updates, and we try to work with projects when their mirrors are broken. [Here](https://landscape.riscv.org/card-mode?license=open-source&grouping=no&sort=latest-commit) is view of projects sorted by last update.

We generally remove closed source products when they have not tweeted in over 3 months. This doesn't apply to Chinese companies without Twitter accounts, since Twitter is blocked there. [Here](https://landscape.riscv.org/card-mode?license=open-source&grouping=no&sort=latest-tweet) is a view of products sorted by last tweet.

Items that have been removed can apply to be re-added using the regular New Entries criteria above.

## License

This repository contains data received from [Crunchbase](http://www.crunchbase.com). This data is not licensed pursuant to the Apache License. It is subject to Crunchbase’s Data Access Terms, available at [https://data.crunchbase.com/v3.1/docs/terms](https://data.crunchbase.com/v3.1/docs/terms), and is only permitted to be used with this Landscape Project which is hosted by the Linux Foundation.

Everything else is under the Apache License, Version 2.0, except for project and product logos, which are generally copyrighted by the company that created them, and are simply cached here for reliability. The trail map, static landscape, serverless landscape, and [landscape.yml](landscape.yml) file are alternatively available under the [Creative Commons Attribution 4.0 license](https://creativecommons.org/licenses/by/4.0/).

## Formats

The RISC-V Ecosystem Landscape is available in these formats:

* [PNG](https://landscape.riscv.org/images/landscape.png)
* [PDF](https://landscape.riscv.org/images/landscape.pdf)

## Installation

You can install and run locally with the [install directions](INSTALL.md). It's not necessary to install locally if you just want to edit [landscape.yml](landscape.yml). You can do so via the GitHub web interface.

## Vulnerability reporting

Please open an [issue](https://github.com/riscv-admin/riscv-landscape/issues/new/choose) or, for sensitive information, email info@riscv.org.
