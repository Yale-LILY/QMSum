# QMSum

### Overview

This repository maintains dataset for NAACL 2021 paper: "QMSum: A New Benchmark for Query-based Multi-domain Meeting Summarization".

**QMSum** is a new human-annotated benchmark for query-based multi-domain meeting summarization task, which consists of 1,808 query-summary pairs over 232 meetings in multiple domains.

If you use our dataset, please limit it to research purposes and cite our paper.

### Dataset
You can access the train/valid/test set of QMSum through the ```data/ALL``` folder. In addition, QMSum is composed of three domains: ```data/Academic```, ```data/Product``` and ```data/Comittee``` contain data in a single domain.

Files in each folder:

* ```jsonl```: data in .jsonl format.
* ```all```: all data in .json format.
* ```train```: training data.
* ```val```: validation data.
* ```test```: test data.

The format of json data is as follows:

```
{
    "topic_list": [
        {
            "topic": "Introduction of petitions and prioritization of governmental matters",
            "relevant_text_span": [["0","19"]]
        },
        {
            "topic": "Financial assistance for vulnerable Canadians during the pandemic and beyond",
            "relevant_text_span": [["21","57"], ["113","119"], ["191","217"]]
        },
        ...
	],
    "general_query_list": [
        {
            "query": "Summarize the whole meeting.",
            "answer": "The meeting of the standing committee took place to discuss matters pertinent to the Coronavirus pandemic. The main issue at stake was to ..."
        },
        ...
    ],
    "specific_query_list": [
        {
            "query": "Summarize the discussion about introduction of petitions and prioritization of government matters.",
            "answer": "The Chair brought the meeting to order, announcing that the purpose of the meeting was to discuss COVID-19 's impact on Canada. Five petitions were presented ...",
            "relevant_text_span": [["0","19"]]
        },
		{
            "query": "What did Paul-Hus think about the introduction of petitions and prioritization of government matters?",
            "answer": "Mr. Paul-Hus thought that the government should not take firearms away from law-abiding Canadian citizens. He inquired into ...",
            "relevant_text_span": [["9","18"]]
        },
        ...
    ],
    "meeting_transcripts": [
        {
            "speaker": "The Chair (Hon. Anthony Rota (NipissingTimiskaming, Lib.))",
            "content": "I call the meeting to order.  Welcome to the third meeting of the House of Commons Special Committee on the COVID-19 Pandemic ..."
        },
        {
            "speaker": "Mr. Garnett Genuis (Sherwood ParkFort Saskatchewan, CPC)",
            "content": "Mr. Chair, I'm pleased to be presenting two petitions today. The first petition is with respect to government Bill C-7 ..."
        },
        ...
		{
            "speaker": "Hon. Seamus O'Regan",
            "content": "Mr. Chair, we have been working with our provincial partners. We have been working with businesses of all sizes in the oil and gas industry ...."
        },
        {
            "speaker": "The Chair",
            "content": "That's all the time we have for questions today. I want to thank all the members for taking part. The committee stands adjourned until tomorrow at noon.  The committee stands adjourned until tomorrow at noon. Thank you."
        }
    ]
}
```
Please note that there may be multiple relevant text spans for a topic or a specific query. The general query has no corresponding text spans because it corresponds to the entire meeting transcript.

### Statistics
<p align="justify">
  <img src="https://github.com/Yale-LILY/QMSum/blob/main/figures/Statistics.jpg" alt="statistics">
</p>

### Experimental Results
<p align="center">
  <img src="https://github.com/Yale-LILY/QMSum/blob/main/figures/Experimental%20Results.jpg" width="350" alt="statistics">
</p>
