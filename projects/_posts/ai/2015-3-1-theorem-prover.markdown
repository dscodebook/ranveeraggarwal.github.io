---
layout: project
categories: projects
title: "Automated Theorem Prover"
tyf: Project
---
####Problem Statement:
Here, we build an automated theorem prover to search for proofs of arbitrary formulae under the axioms of Propositional Calculus.

####To Run:
Put the expressions you wish to prove in `expressions.ini`  
Then open up the terminal and enter:

    python theoremProver.py

####Working of the code:
We extensively use the deduction theorem to find whether the prove for an expression exists. Here's how it works:

* We take each expression
* We separate hypotheses by bringing terms to the LHS (see format mentioned in report)
* We repeatedly apply *Modus Ponens* to get smaller and smaller terms
* We try to prove **F #22A2; F** using the smaller terms
* If we are unable to, we ask the user to give inputs as axioms
* We repeatedly ask user for axiom inputs until the theorem gets proved or the user gives up

####Report
The report can be found <a href="/docs/projects/ai/theorem-prover/report.pdf">here</a>.

####Source Code
The source code can be found <a href="https://github.com/ranveeraggarwal/theorem-prover">here</a>.