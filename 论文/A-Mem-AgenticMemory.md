
<img width="826" height="412" alt="image" src="https://github.com/user-attachments/assets/1ddea44c-6a67-45d2-97d5-502a93cef3cc" />


视频讲述了对Arxiv 2025年2月发布的论文《A-Mem: Agentic Memory for LLM Agents》的速览，介绍了该论文针对传统记忆系统的问题提出的创新方法、框架流程及关键亮点，具体如下：
- **论文基本信息与传统记忆系统问题**：论文于ARCAVE2025年2月挂上，当时引用量已达60；指出传统memory system的workflow模式固定，读、写及memory结构、检索和更改方式需人为预先设计，较为死板，无法适用多样化场景。
- **A-Mem方法核心创新点**：一是引入大模型协助管理memory，即Agentic Memory；二是写入当前交互内容到memory时，会同步更新过往的memory，而非仅存储当前内容。
- **A-Mem框架之记忆笔记生成**：当agent与环境产生交互时，先使用协助管理memory的大模型总结交互内容，写成包含时间、内容、关键词、标签等attributes的note，将关键信息提取后与原内容一同放入notes。
- **A-Mem框架之相关记忆检索与筛选**：用embedding模型将note转化为向量，在memory中检索匹配的相关记忆，先通过相似度匹配选出top k相似记忆；之后让大模型对top k记忆再次筛选，过滤掉大模型认为不相关的记忆，仅保留相似度高且确实相关的记忆，并将其与当前交互过程放入同一个box，且一个memory note可能同时存在于多个box。
- **A-Mem框架之记忆演化过程**：接收新memory后，让大模型判断是否需要根据新memory更新包含相关记忆的box，若需要则实时更新过往memory；并举例说明，如用户先询问编程课程推荐，后提及自己是课业忙的学生并求推荐短时长电影，大模型会更新此前“用户想学编程”的记忆，补充“用户是课业重的学生”这一信息，以便后续更好推荐。
- **A-Mem框架之记忆检索使用**：当有问题需要检索记忆时，先让text model将问题编码成embedding，在memory中检索出top k记忆；之后不仅拿出检索到的记忆，还会将该记忆所在box内的所有记忆一同作为相关memory反馈给agents，供其参考以提升效果。
- **论文总结与后续建议**：认为A-Mem思路方法简单，memory evolution过程是较新颖且关键的地方；同时提到论文内有更多细节描述，建议感兴趣者详细阅读原文。


<img width="988" height="500" alt="image" src="https://github.com/user-attachments/assets/11975cbe-46dc-44e2-846a-49be4a440cd0" />


