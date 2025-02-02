---
layout: page
title: Set up the GUAC Visualizer
permalink: /guac-visualizer/
parent: GUAC demos
grand_parent: Getting started with GUAC
nav_order: 6
---

# Set up the GUAC Visualizer

The GUAC Visualizer is an experimental utility that can be used to interact with
GUAC services. It acts as a way to visualize the software supply chain graph, as
well as a means to explore the supply chain and prototype policies.

{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

## Requirements

- [Git](https://git-scm.com/downloads)
- [Yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable)
- [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
- A fresh copy of the [GUAC service infrastructure through Docker Compose]({{
  site.baseurl }}{%link setup.md %}).

## Step 1: Getting started

1. If you haven't already, download the main GUAC version `v0.1.2` from
   [this link](https://github.com/guacsec/guac/releases/tag/v0.1.2).
   - Follow steps 2-5 in [setup]({{ site.baseurl }}{% link setup.md %}).
2. Download the specific GUAC visualizer version `v0.1.1` from
   [this link](https://github.com/guacsec/guac-visualizer/releases/tag/v0.1.1)
   and extract it in the same path as your GUAC repo.

Change directories into the visualizer's repo:

```bash
cd path/to/guac-visualizer
```

All commands run throughout this guide should be in this working directory.

## Step 2: Running the visualizer from source

1. Install the guac-visualizer dependencies:

   ```bash
   yarn install
   ```

   The output should look like:

   ```
   $ yarn install
   yarn install v1.22.19
   warning package-lock.json found. Your project contains lock files generated by tools other than Yarn. It is advised not to mix package managers in order to avoid   resolution inconsistencies caused by unsynchronized lock files. To clear this warning, remove package-lock.json.
   [1/4] 🔍  Resolving packages...
   [2/4] 🚚  Fetching packages...
   warning Pattern ["@apollo/client@latest"] is trying to unpack in the same destination "/Users/lumb/Library/Caches/Yarn/v6/npm-@apollo-client-3.7.12-  9ddd355d0788374cdb900e5f40298b196176952b-integrity/node_modules/@apollo/client" as pattern ["@apollo/client@^3.7.10"]. This could result in non-deterministic
   behavior, skipping.
   [3/4] 🔗  Linking dependencies...
   warning "@graphql-codegen/cli > @graphql-tools/code-file-loader > @graphql-tools/graphql-tag-pluck > @babel/plugin-syntax-import-assertions@7.20.0" has unmet peer   dependency "@babel/core@^7.0.0-0".
   warning " > @graphql-codegen/typescript-react-apollo@3.3.7" has unmet peer dependency "graphql-tag@^2.0.0".
   warning "cosmos-over-cytoscape > html-webpack-plugin@5.5.0" has unmet peer dependency "webpack@^5.20.0".
   warning " > react-paginated-list@1.1.6" has incorrect peer dependency "react@>=16.8.25 <=16.13.1".
   warning " > react-paginated-list@1.1.6" has incorrect peer dependency "react-dom@>=16.8.25 <= 16.13.1".
   warning " > react-paginated-list@1.1.6" has incorrect peer dependency "styled-components@>=4.4.1 <= 5.1.1".
   warning " > styled-components@5.3.9" has unmet peer dependency "react-is@>= 16.8.0".
   [4/4] 🔨  Building fresh packages...
   ✨  Done in 12.78s.
   ```

## (Optional) : Configuration

By default, the GUAC Visualizer assumes that the GraphQL server is running on
http://localhost:8080/query. However, you can optionally configure the
visualizer to connect to a different GraphQL endpoint or to read from a
`guac.yaml` config file from your curent working directory.

## Step 3: Running the visualizer locally:

```bash
yarn dev
```

The output should look like:

```
$ yarn dev
yarn run v1.22.19
$ next dev
ready - started server on 0.0.0.0:3000, url: http://localhost:3000
info  - Using webpack 5. Reason: Enabled by default https://nextjs.org/docs/messages/webpack5
```

You can then go to [localhost:3000](http://localhost:3000) in your browser to
see the graph visualization.

<hr />
<br />

### Using the GUAC visualizer will look something like this:

<br />

![image](https://github.com/guacsec/guac-visualizer/assets/68356865/0f60b7f8-c81d-424d-99a2-f3b365e388dc)
