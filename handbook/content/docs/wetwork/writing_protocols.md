---
# This is the page metadata header. It is written in YAML format
# Full reference: https://github.com/alex-shpak/hugo-book/tree/master#page-configuration
title: "Writing Protocols" # The page title. Will show up in the index only
weight: 1 # Pages with more weight will show up higher in the index. Pages with the same weight are ordered alphabetically
desc: "How to structure and write wet-lab protocols" # The description to be used in the index files.
draft: false # If this is true, the page will not be included in the live site or the indexes.

# Optional:
#bookCollapseSection: true # Will collapse other pages in this section. Useful in _index.md pages
#bookFlatSection: true # Opposite of 'bookCollapseSection', and the default.
#bookTOC: false # Hide the TOC in this page
#bookSearchExclude: true # Hide this page from search results. Useful in _index.md pages.
---

# Writing Protocols
> How to structure and write wet-lab protocols
![Draft](https://img.shields.io/badge/status-draft-red)

{{< hint warning >}}
This page is still a draft because I'm still writing it.
{{< /hint >}}

## Aim
This page describes guidelines on how to write wet-lab protocols.

## Introduction
Documenting your wet-lab work is essential for a variety of reasons.
The most important reason, however, probably is reproducibility.
If you work is not reproducible, it is essentially useless.

For this reason, documenting *how* you ran an experiment is essential.
It is also very easy to get wrong.
Here, I'll try to show an easy-to-use and yet formal way to structure your
experimental protocols with future reproducibility in mind.

### References
Most of this text is built on top of these references:
- [Giraldo et. al. (2018) - *A guideline for reporting experimental protocols in life sciences.*](https://doi.org/10.7717/peerj.4795)

## Definitions
First of all, it's useful to have some definitions.
When you run a procedure in the lab, you will probably refer to it as an "experiment".
However, it's important to distinguish between a procedure that performs a function
purely for "practical" needs and one that instead has a broader purpose, such
as collecting information to answer an experimental question.

For this reason, I'll adopt the following terminology:
- A **protocol** is a series of steps that perform a function.
  For example, cultivating cells to obtain more cells is a protocol: you have
  to follow a series of steps to go from a few cells (your starting point) to
  many cells (your end goal).

  A protocol has a defined (physical) *input* and a defined (physical) *output*.
  A protocol may or may not produce some *data* as well.
- An **experiment** is a series of protocols aimed at collecting data to
  answer an experimental question.
  For instance, when you perform a western blot, you want to collect data on
  wheter a certain protein is expressed or not.
- A **project** is a series of experiments all aimed at answering a certain
  question or delucidating a certain topic.
  A project is generally aligned to what you think when you read a publication.

A protocol always has a defined **input** and a defined **output**.
A protocol that has no input in a **generative** protocol.
A protocol that has no output is a **destructive** protocol.
A protocol that produces data is a **measuring** protocol.

An experiment is generally composed of different protocols all "joined together"
to form a larger unit with a greater purpose.
Generally, an experiment starts with one (or more) generative protocols and
ends with one (or more) destructive protocols.
The ultimate goal of an experiment is usually to produce some data.
Therefore, some of the experiment procols are measuring, most often the last
ones in the experiment.

// TODO: add a flowchart of the general structure.

Why would you use such a structure for your protocols?
Well, I see many benefits in using this method:
- It forces you to break down your long experiments (which you probably called
  protocols) into manageable chunks.
  - This helps with organization (each protocol has a defined timeframe and 
    provides focused steps on what to do and how) as well as aiding sample
    labelling and storage (each generative protocol details how to label and
    store each generated sample).
  - Having broken down steps makes your protocols reusable in many different
    stuations, saving you time when designing new experiments.
- It helps to clearly define objectives when you actually go and run your
  experiment (e.g. each protocol has a very precise goal).
- It helps with efficiency (each protocol has defined time requirements, making
  it easy to run different protocols in parallel if you need to).
- It standardizes the way that you run your experiments by making the same
  steps in different experiments actually the same.
- It makes it easy to report your results, as you can simply talk about each
  protocol as a separate section in your, say, weekly report.
- It clearly defines what data and metadata each protocol generates and how
  (as well as if) you should store it for later reference.
- Having clear names for each of your experimental steps makes it clearer when
  you communicate with your peers of what you have done and what might have
  gone wrong ("The General mRNA Extraction protocol has failed..." is better than
  "something might have gone wrong with the mRNA?").
- It helps clearly think about what an experiment does and how it does it.
- It helps when adapting old experiments to new variables (e.g. by swapping
  out compatible steps).

With this in mind, we can think what in practice are protocols, experiments and
projects.
I can think of nothing better than some examples:
- A western blot is an *experiment*;
- A procedure to culture some particular cell type is a *protocol*;
- A way to extract proteins from a suspension of cells is a *protocol*;
- A method of exploring how a drug affects the behaviour of some cells is a *project*;
- A way to generate the 3D structure of a protein is an *experiment*;

Ultimately, the finer split between protocol, experiment and project is up to
the experimenter, but I believe they are well defined.

## Writing protocols and experiments
Now that we have definitions out of the way, we can delve into *what* to write
in these protocols and experiments.

When writing a protocol we must keep in mind these principles:
- It must be **unambiguous**: anyone reading the protocol should be able to run it.
- It must clearly define what it needs and what it produces.
- It must define what metadata is important to annotate along the way for
  future data storage.
- It must be static, e.g. it must be findable in perpetuity (if we ever need to
  re-run an old experiment).
- It must give credit to whoever designed it, tested it, or validated it.

With this in mind, we can defined what are the *minimal* things that we have to
specify when writing protocols:
- The **author** of the protocol;


