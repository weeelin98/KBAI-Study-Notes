### A. 结构化知识框架 (Module 13: Planning)

**1.0 规划 (Planning) 的定义与目标** 1.1 **核心定义**: 规划是一种强大的行动选择方法 (a powerful method for action selection) 。 1.2 **基本过程**: 智能体将感知历史 (perceptual histories) 映射为行动 (actions) 。 1.3 **技术基础**: 使用从逻辑模块学到的语法来设定目标 (goals)、状态 (states) 和操作符 (operators) 。 1.4 **核心挑战**: 1.4.1 当存在多个目标时，它们之间可能会产生冲突 (conflicts) 。 1.4.2 如何系统地组织各种操作符以避免冲突 。

**2.0 规划问题的形式化表示 (Formal Representation)** 2.1 **状态 (States)** 2.1.1 **定义**: 对世界在特定时刻的描述，由一组命题逻辑断言 (assertions) 的合取 (conjunction) 构成 。 2.1.2 **初始状态 (Initial State)**: 规划开始时世界的状态 。 - _示例 (油漆问题)_: `On(Robot, Floor) & Dry(Ladder) & Dry(Ceiling)` 。 2.1.3 **目标状态 (Goal State)**: 希望达到的世界状态，同样由命题的合取表示 。 - _示例 (油漆问题)_: `Painted(Ceiling) & Painted(Ladder)` 。 2.2 **目标 (Goals)** 2.2.1 使用命题逻辑表示 。 2.2.2 多个目标通过合取 (conjunction) 连接 。 2.2.3 **作为控制知识 (Control Knowledge)**: 目标提供了选择操作符的隐性知识 (tacit knowledge)，帮助决定在众多可能的操作中选择哪一个以更接近目标 。 2.3 **操作符 (Operators)** 2.3.1 **定义**: 用于在不同状态之间转换的行动模型 。 2.3.2 **结构**: - **前置条件 (Preconditions)**: 应用该操作符前世界必须为真的断言集合 。按照惯例 (STRIPS planner)，前置条件中只包含肯定文字 (positive literals) 。 - **后置条件 (Post-conditions)**: 应用该操作符后世界变为真的断言集合，可以包含否定文字 (negative literals) 。 2.3.3 **应用语义**: 只有当世界状态满足其所有前置条件时，操作符才能被应用 。

**3.0 规划方法与技术** 3.1 **规划与状态空间搜索 (Planning and State-Space Search)** 3.1.1 规划可以被看作是在一个由状态和操作符构成的巨大空间中寻找从初始状态到目标状态的路径 。 3.1.2 弱AI方法 (如 Means-Ends Analysis) 可以作为一种启发式方法来选择操作符以减小当前状态与目标状态的差异 。 3.2 **线性规划 (Linear Planning) 与其局限性** 3.2.1 **定义**: 假设目标可以按任意顺序独立实现的简单规划器 。 3.2.2 **目标冲突 (Goal Clobbering)**: 实现一个目标的计划可能会破坏 (clobbers) 实现另一个目标的条件 。 - _示例 (油漆问题)_: `paint-ladder` 操作的后置条件 `Not(Dry(Ladder))` 与 `climb-ladder` 操作的前置条件 `Dry(Ladder)` 冲突 。 3.3 **部分有序规划 (Partial-Order Planning / Non-linear Planning)** 3.3.1 **核心思想**: 将多个目标视为相互独立的，为每个目标生成部分计划，然后检测并解决这些计划之间的冲突 。 3.3.2 **过程**: 1. **独立规划**: 为每个目标生成一个独立的、线性的行动序列（部分计划） 。 2. **冲突检测**: 检查一个计划中的某个状态是否与另一个计划中某个操作符的前置条件相冲突（即互为否定） 。 3. **冲突解决**: 通过对目标进行排序（提升 promoting 或降低 demoting 某个目标的优先级）来解决冲突，确保有冲突的操作在破坏条件的状态发生之前完成 。 4. **开放前置条件 (Open Preconditions) 处理**: 在合并计划时，如果一个操作符的前置条件未被满足，则需要插入新的操作符来满足该条件 。 3.4 **层级规划 (Hierarchical Planning)** 3.4.1 **动机**: 现实世界的问题可能非常复杂，会导致状态空间爆炸和过长的计划 。 3.4.2 **核心思想**: 在多个抽象层次上进行思考，将复杂的底层操作抽象成高层的宏操作符 (macro operators) 。 3.4.3 **层级任务网络 (Hierarchical Task Networks - HTN)**: 一种用于表示层级计划的知识表示法，宏操作符可以被分解为更底层的操作 。 - _示例 (积木世界)_: `unstack` 和 `stack-ascending` 作为宏操作符，各自可以分解为一系列的 `move` 操作 。

**4.0 规划与智能的关联 (Cognitive Connection)** 4.1 **行动选择的核心**: 规划是智能体进行行动选择的核心过程 。 4.2 **多目标管理**: 认知智能体通常有多个可能相互作用（积极或消极）的目标，规划是同时实现多个目标的核心过程 。 4.3 **使隐性过程显性化**: AI中的规划算法将人类看似毫不费力的规划过程（如解决油漆问题）中的每一步都明确、精确地定义出来，从而为人类认知过程提供了可检验的假设 。 4.4 **思维社会 (Society of Mind)**: 部分有序规划可以看作是多个简单智能体（如计划生成器、冲突检测器、冲突解决器）相互协作产生复杂行为的例子 。

### B. 文本思维导图 (Module 13: Planning)

- **Planning (规划)**
    
    - - **定义**: 一种强大的行动选择方法 (action selection) 。
            
    - - **基础**: 使用逻辑语法 (logic syntax) 来定义:
            
            - **States (状态)**: 对世界状态的描述，是命题的合取 。
                
                - - **Initial State (初始状态)**
                        
                - - **Goal State (目标状态)**
                        
            - **Goals (目标)**: 期望达到的状态，作为指导行动的“控制知识” (Control Knowledge) 。
                
            - **Operators (操作符)**: 用于状态转换的模型 。
                
                - - **Preconditions (前置条件)**: 操作前必须满足的条件 。
                        
                - - **Post-conditions (后置条件)**: 操作后改变的状态 。
                        
    - - **核心问题**:
            
            - **多目标冲突 (Conflicts between multiple goals)**
                
            - **目标冲突 (Goal Clobbering)**: 一个计划破坏了另一个计划的条件 。
                
    - - **主要方法**
            
            - **线性规划 (Linear Planning)**
                
                - - **局限**: 无法处理目标间的冲突 。
                        
            - **部分有序规划 (Partial-Order Planning)**
                
                - - **别名**: 非线性规划 (Non-linear Planning) 。
                        
                - - **流程**:
                        
                        - 1. 为每个目标独立生成 **部分计划 (Partial Plan)** 。
                            
                        - 2. **检测冲突 (Detect Conflicts)**: 检查一个计划的状态是否否定了另一个计划的前置条件 。
                            
                        - 3. **解决冲突 (Resolve Conflicts)**: 通过对目标排序 (promoting/demoting) 来解决 。
                            
                        - 4. 解决 **开放前置条件 (Open Preconditions)** 问题 。
                            
            - **层级规划 (Hierarchical Planning)**
                
                - - **动机**: 应对复杂问题和状态空间爆炸 。
                        
                - - **表示法**: **层级任务网络 (Hierarchical Task Networks - HTN)** 。
                        
                - - **核心**: 使用 **宏操作符 (Macro Operators)** 在不同抽象层次上进行规划 。
                        
    - - **与认知的联系 (Cognitive Connection)**
            
            - - **行动选择**: 规划是认知中行动选择的核心 。
                    
            - - **多目标处理**: 认知智能体通过规划管理多个目标 。
                    
            - - **思维的显性化**: AI规划算法能将人类的内隐规划过程明确化 。
                    
            - - **思维社会理论 (Society of Mind)**: 规划过程可看作多个简单智能体的协作 。