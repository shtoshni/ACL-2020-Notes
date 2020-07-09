# Interactive Machine Comprehension with Information Seeking Agents
## By Xingdi Yuan, Jie Fu, Marc-Alexandre Côté, Yi Tay, Chris Pal, Adam Trischler

* Current QA systems assume all the supporting documents to be "observable".
* With web-level corpuses, that's not possible.
* The authors present a interactive game where the agent can pass in commands to reveal more text.
* In static QA datasets, we can do this by revealing one sentence at a time resulting in iSQuAD from SQuAD.
* The agent can gather information as the document is revealed, however, there's a memory bottleneck. The memory bottleneck prevents it from revealing the whole text and answering like a standard QA system.
* There's a huge performance gap due to the restrictions posed by this game.
* I think this is still preliminary work because a lot of the standard tools of the trade are missing. 
