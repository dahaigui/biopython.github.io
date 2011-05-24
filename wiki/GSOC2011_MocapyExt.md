---
title: GSOC2011 MocapyExt
permalink: wiki/GSOC2011_MocapyExt
layout: wiki
---

BioPython is a very popular library in Bioinformatics and Computational
Biology. Mocapy++ is a machine learning toolkit for training and using
Bayesian networks. However, Mocapy++ is implemented in C++ and its
monolithic architecture does not provide any mechanism to plug-in new
node types (probability distributions/densities) without prior source
code conversion to C++ and the recompilation of the library. The goal of
this project is to develop an easy-to-use plug-in system for Mocapy++,
which would allow to load and test probability distributions on the fly.
If a user is working in C++, the user could load/embed arbitrary
probability distributions in Mocapy++ and then proceed to use them in a
familiar manner.

Introduction
------------

Author & Mentors
----------------

[Justinas V. Daugmaudis](User%3AJustinas_Daugmaudis "wikilink")
vygis.d@gmail.com

**Mentors**

  
Thomas Hamelryck

Eric Talevich

Work Plan
---------

'''Gain understanding of S-EM and directional statistics '''

-   Review the course material in SCI-B2-1011-Structural bioinformatics;

<!-- -->

-   Study the theory for Markov chain Monte Carlo methods and dynamic
    Bayesian networks;

<!-- -->

-   Supplement the base knowledge by reading relevant papers.

'''Study of Mocapy++ use cases '''

-   Study the Mocapy++ implementation of Stochastic Expectation
    Maximization (S-EM) and parameter learning of Bayesian networks;

<!-- -->

-   Review examples distributed with Mocapy++ library.

'''Study of Mocapy++ internals and code '''

-   Distill the relevant concepts for nodes and densities. Currently,
    there are no such concepts defined within the Mocapy++ framework;

<!-- -->

-   Compare with other examples that implement
    probability distributions.

'''Design of Mocapy++ plugin interface '''

-   Plugin module has to implement the model of
    NodeConcept/DensityConcept;

<!-- -->

-   All the models have to be uniformly accessible through the
    plugin system.

'''Implement Mocapy++ plugin module '''

-   Implement test cases in C++ using the new plugin interface;

<!-- -->

-   Provide Python bindings for the defined interface;

<!-- -->

-   Implement test cases in Python. Verify that this plugin system can
    be used transparently in Python.

'''Experiment with the modular Mocapy++ architecture '''

-   Create sample applications that showcase the advantages of
    modularity that is provided by the plugin system in Mocapy++;

<!-- -->

-   Measure performance.

Project Schedule
----------------

'''Week 1-2 \[May 23th -- June 5th\] '''

Design of interface strategy: it is hard to overstate the importance of
the bindings' API feeling "natural" to a BioPython user. So much of the
time will be devoted to the design of the interface.

'''Week 3-5 \[June 6th -- June 19th\] '''

Implementing Python bindings using Boost.

'''Week 6-7 \[June 20th -- June 30th\] '''

Convert some examples that would showcase Mocapy++ BioPython bindings in
action (like hidden Markov model with a von Mises output node, hidden
Markov model on torus, simple hidden Markov model, etc).

'''Week 7-8 (Midterm) \[July 1st -- July 10th\] '''

-   Thoroughly testing and consolidating the features. Writing the
    documentation for each feature.

<!-- -->

-   Mid-term Evaluations. Discuss with the mentor the state of the
    project and adjust the schedule to comply with project's needs.

'''Week 9-10 \[July 11th -- July 24th\] '''

Example applications, involving Bio.PDB data mining

'''Week 11-12 \[July 25th -- August 7th\] ''' Update the documentation
to reflect the new functions. Also document the examples, do any scrub
work of code, etc. Planned 'pencils down' date.

'''Week 13-14 \[August 8th -- August 21st\] '''

Introduce the bindings to the wider audiences, gather the opinions and
the reviews in community.

'''Week 15 \[August 22nd\] ''' The end of the project.