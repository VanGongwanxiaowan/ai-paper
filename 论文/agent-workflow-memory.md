视频讲述了ICML2025一篇关于Agent记忆的论文《Agent Workflow Memory》，介绍其提出的问题、核心方法、工作流构成、应用场景及实验效果，具体如下：
- **提出研究问题**：当前大模型Agent虽有较强能力，但处理长且复杂的任务时能力有限；而人类可通过过往经验处理复杂任务，故研究如何让Agent从自身过往经验中提升处理新的复杂问题的能力。
- **核心方法介绍**：引入“workflow（工作流）”概念，将Agent之前解决任务的工作流存储到其记忆（memory）中；Agent每次解决新问题时，会从记忆中寻找类似经验作为参考，且会把新解决问题的工作流也存入记忆，以“滚雪球”式积累经验，增强处理复杂问题的能力。
- **方法效果示例**：以找地方相关任务为例，Agent先将“通过名字在地图找地方”的工作流存入记忆，后续遇到“找某地附近咖啡厅”“找某地坐标”等更复杂任务时，可参考过往工作流完成；实验中，该方法（AWM）在40个示例上的准确率比普通baseline高22.5%。
- **工作流构成**：包含工作流描述（说明工作流用途）、工作流轨迹（解决任务的流程）；轨迹每一步又包括三部分，分别是用自然语言描述当前环境状态、Agent下一步要做的事、下一步要调用的函数或工具。
- **工作流泛化处理**：总结工作流时，不使用具体任务描述，而是将其中具体信息替换为抽象名词，如把“找巴黎铁塔位置”改为“找某个地方位置”，以此增强Agent处理同类问题的泛化能力。
- **两种应用场景**：一是离线场景（offline），提前将多个成功任务的工作流存入记忆，Agent处理新问题时直接参考这些固定记忆，记忆不实时增长；二是在线场景（online），初始记忆为空或仅有少量信息，Agent解决新问题后，经LM评测确认成功，就将该任务工作流存入记忆，记忆随任务解决不断迭代增长。
- **实验部分概述**：主要展示实验效果与消融实验，从图中可看出Agent在40个样本时能较快达到稳定效果，前期能力提升迅速，且在不同数据集上从解决任务所需步骤数和准确率两方面进行了对比。


<img width="577" height="309" alt="image" src="https://github.com/user-attachments/assets/a6db37a7-35bf-49f6-9a62-3776c56848a5" />



<img width="560" height="462" alt="image" src="https://github.com/user-attachments/assets/112765ca-6711-41fa-acb2-01525cdb2782" />



<img width="497" height="323" alt="image" src="https://github.com/user-attachments/assets/e2d294db-4d9c-404a-9977-e3c2a14f482c" />


<img width="547" height="337" alt="image" src="https://github.com/user-attachments/assets/4b559b22-bc8a-410f-bff4-0358740c2b12" />


<img width="514" height="409" alt="image" src="https://github.com/user-attachments/assets/c2f18f43-dce1-478a-8859-ce81a250ebbf" />
