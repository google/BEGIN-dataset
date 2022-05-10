BEGIN
=====

https://github.com/google/BEGIN-dataset

A benchmark dataset for evaluating dialog system and natural language
generation metrics.  See our paper "Evaluating Groundedness in
Dialogue Systems: The BEGIN Benchmark" at
https://arxiv.org/abs/2105.00071 .

BEGIN is a Benchmark for evaluating response attribution to some given
background knowledge. It is comprised of 12k dialogue turns generated
by state-of-the-art dialogue systems trained on three widely used
knowledge-grounded dialogue benchmarks, and annotated by humans for
the attribution of responses.

Using BEGIN, we analyze the robustness of 8 evaluation metrics. We
find that simply resorting to correlation with human judgment is not
sufficient to draw conclusions about the effectiveness of the metrics.
More specifically, we observe that these metrics rely heavily on
spurious correlations and perform poorly on attributable abstractive
responses confounding them with unattributable ones.  Finally, we find
that these metrics perform substantially worse when tested on
benchmarks with long knowledge sources, corroborating inherent
robustness issues under distribution shift.

This is not an officially supported Google product. This means that
Google may not regularly release updates or provide support in
conjunction with your use of this dataset.


Authors
-------
* Nouha Dziri
* Hannah Rashkin <hrashkin@google.com>
* Tal Linzen <linzen@google.com>
* David Reitter <reitter@google.com>


Data Format
----------
We split BEGIN into 90% test set and 10% development set,
and store them in a tsv (tab-separated) format. Below, we define each column:

    model name          The dialogue model used to generate responses
	                    (gpt2, t5, ctrl [CTRL-Dialog], doha)
    data_source         The dialogue benchmark used to train the models
	                    (wow [Wiz. of Wikipedia], cmu [CMU DoG], tc [Topical Chat])
    knowledge           The knowledge-snippet on which the response should be grounded
    message             The previous turn in the dialogue history
    response            The generated response
    begin_label         BEGIN label (Fully attributable, Not fully attributable, Generic)


Documentation
-------------
Note that the dataset has been revised as compared to the initial preprint.

https://arxiv.org/abs/2105.00071


## Citation
This work has been submitted to TACL, and we are still awaiting the decision. In the meantime, please cite our work if 
you use BEGIN in your research.
```
@article{dziri2021evaluating,
  title={Evaluating groundedness in dialogue systems: The begin benchmark},
  author={Dziri, Nouha and Rashkin, Hannah and Linzen, Tal and Reitter, David},
  journal={arXiv preprint arXiv:2105.00071},
  year={2021}
}
```


Versions
--------
* Example release 6/1/2021: Only examples included
* First full release 6/1/2021
* Second full release 6/1/2022: New data collection methodology
  * We changed to a simplified annotation question design.
  * We added output from two additional models (Doha and Ctrl-Dialog). 
  * We added two datasets, TopicalChat and CMU-Dog.
