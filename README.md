# LangGPT-tools
![langgpt](https://github.com/sci-m-wang/LangGPT-tools/blob/main/figures/langgpt.png)
This project provides templates and the sft adapters of LLMs based on [LangGPT](https://github.com/langgptai/LangGPT), as well as the experiments covered in the paper that [LangGPT: Rethinking Structured Reusable Prompt Design Framework for LLMs from the Programming Language](https://arxiv.org/abs/2402.16929). The adapters can be found at [Huggingface/LangGPT](https://huggingface.co/langgptai).

## About LangGPT
LangGPT is a prompt design framework as the programming language for LLMs. LangGPT refers to the systematic, prescriptive, and reusable properties of programming languages, and retains the flexibility and extensibility of natural languages. LangGPT is designed as a dual-layer structure, which consists of modules and internal elements. Modules in LangGPT can be divided into two categories: inherent modules and extension modules. For inherent modules, we design the necessary internal elements of each module in detail and give example templates. In addition, for the extension modules, we unified the design of the basic internal elements.

To systematically design prompts that meet the principles, we have made full reference to the design ideas and structures of object-oriented programming languages. We consider the prompt as a software project and analogize the prompt design process with the software development process. The correspondence is shown following:

![correspondence](https://github.com/sci-m-wang/LangGPT-tools/blob/main/figures/correspondence.jpg)

Based on analogical analyses, it can be found that natural language prompts have a similar multi-level structure as programming languages. Therefore, we refer to the structure of programming languages propose a dual-layer structure for prompt design, and define the notion of module and element for prompts.

## Modules
A complete prompt contains several modules. Modules are similar to classes in programming languages, and each module represents an aspect of the requirements for LLMs. For instance, prompts can be augmented in terms of constraints, goals, profiles, etc. Within a module, a number of internal elements are included. Elements are similar to functions and properties in programming languages and represent the content of direct and specific instructions to LLMs. For example, `Output should be no more than 500 words` could be an element in a prompt that belongs to the module **constraint**.

A dual-layer structure can be a good way to standardize the formatting of prompts. However, the flexibility of natural languages would be lost if prompts are too strictly required to follow predefined standard modules and internal elements. In addition, it will reduce the generalisability of LangGPT to different tasks in different domains, which is not conducive to the reuse of quality prompts. To solve these problems, we divided the types of modules and elements into prompts. We defined **inherent module** and **basic element** as the predefined dual-layer prompt template. In addition, we constructed extension module and custom element that support customization. We provide both Markdown and JSON formats for inherent modules and extension modules. Furthermore, we have written basic elements for different modules and defined principles for writing custom elements.

![alt text](https://github.com/sci-m-wang/LangGPT-tools/blob/main/figures/image.png)

## Elements
Three purposes are typically included in prompts: (1) Implying a certain message to LLMs; (2) Letting LLMs execute a certain task with or without output; (3) The combination of the first two.

The first of these is very similar to the assignment of properties or variables in programming languages. Correspondingly, the last two categories are similar to functions in programming languages. Thus, we construct these three types of basic elements. We use `The <property> is <value>` to simulate an assignment. For the latter two cases, it is necessary to specify the input information, the task, and the output, where input and output can be omitted. We simulate functions using a form like this: `For the given <property> of <value>, please execute the following actions: <actions>; Return the <result>`. To improve the generalisability and flexibility of prompts, the language can be adapted to express key information. In the following Table, we show some examples of the basic elements in some modules.

![alt text](https://github.com/sci-m-wang/LangGPT-tools/blob/main/figures/elements.png)

## Evaluation
We evaluate the quality of LangGPT prompts by leveraging the prompts to induce LLMs perform tasks of [Open LLM Leaderboard](https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard), whose backend is [lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness). The LangGPT prompts we constructed using the GPT-4 based Agent are [here](https://github.com/sci-m-wang/LangGPT-tools/blob/main/promp4lm-eval-harness).

## Acknowledgement
Thanks to these teams and projects for their support:
- [LangGPT](https://langgptai.feishu.cn/): theoretical support.
- [Intern Studio](https://studio.intern-ai.org.cn): model and GPU support.

## Citation
If you find this project helpful, a star is appreciative. Moreover, you can cite the paper as follow:
```bibtex
@misc{wang2024langgpt,
      title={LangGPT: Rethinking Structured Reusable Prompt Design Framework for LLMs from the Programming Language}, 
      author={Ming Wang and Yuanzhong Liu and Xiaoming Zhang and Songlian Li and Yijie Huang and Chi Zhang and Daling Wang and Shi Feng and Jigang Li},
      year={2024},
      eprint={2402.16929},
      archivePrefix={arXiv},
      primaryClass={id='cs.SE' full_name='Software Engineering' is_active=True alt_name=None in_archive='cs' is_general=False description='Covers design tools, software metrics, testing and debugging, programming environments, etc. Roughly includes material in all of ACM Subject Classes D.2, except that D.2.4 (program verification) should probably have Logics in Computer Science as the primary subject area.'}
}
```

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=sci-m-wang/LangGPT-tools&type=Date)](https://star-history.com/#sci-m-wang/LangGPT-tools&Date)
