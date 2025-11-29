### A. 结构化知识框架 (Module 3: Semantic Networks)

**3.0 知识表示 (Knowledge Representation)**

- **定义**: 知识表示包含两个核心部分：
    
    - **语言 (Language)**: 拥有一套词汇 (vocabulary)。
        
    - **内容 (Content)**: 使用该语言表达的特定知识。
        
- **示例**: 牛顿第二定律 `f = m*a` 。
    
    - 语言是代数方程。
        
    - 内容是力、质量和加速度之间的关系。
        
- **要点**: AI领域发展了多种知识表示法，每种都有其自身的优缺点 (affordances and constraints) 。
    

**3.1 语义网络 (Semantic Networks) 介绍**

- **基本结构**:
    
    - **节点 (Nodes)**: 代表对象 (objects)。
        
    - **带标签的链接 (Labeled Links)**: 代表对象间的关系 (relationships) 。
        
- **构建过程 (以2x1瑞文问题为例)**:
    
    - 1. 识别并表示每个图形中的对象为节点 (e.g., x, y, z) 。
        
    - 2. 表示图形内部对象间的关系为链接 (e.g., y is
        
        `inside` x, z is `above` y) 。
        
    - 3. 表示两个图形间的变换关系为跨图形的链接 (e.g., x is
        
        `unchanged`, y has `expanded`, z is `deleted`) 。
        
- **词汇一致性**: 在解决一类问题时，应使用一套一致的词汇来描述关系和变换 。
    

**3.2 优质知识表示的特征 (Characteristics of Good Representations)**

- **明确性 (Explicit)**: 使关系变得明确 。
    
- **约束性 (Exposing Constraints)**: 揭示问题的自然约束。
    
- **抽象性 (Right Level of Abstraction)**: 捕捉所有必要信息，同时移除不必要的细节 。
    
- **核心品质**:
    
    - 透明 (Transparent)
        
    - 简洁 (Concise)
        
    - 完整 (Complete)
        
    - 快速 (Fast)
        
    - 可计算 (Computable) 。
        

**3.3 应用一：守卫与囚犯问题 (Guards and Prisoners Problem)**

- **问题描述**: 三名守卫和三名囚犯过河，船容量为1-2人，任何岸边囚犯数量都不能超过守卫 。
    
- **语义网络表示**:
    
    - **节点**: 代表问题解决过程中的一个状态 (state) 。例如，左岸有几名守卫、几名囚犯，右岸情况，以及船的位置。
        
    - **链接**: 代表从一个状态到另一个状态的变换或移动 (move) 。
        
    - **链接标签**: 描述移动的具体内容（如一个守卫和一个囚犯移动到对岸）。
        
- **解决过程**:
    
    - 通过构建语义网络，可以将问题求解转化为在状态空间中寻找路径的过程 。
        
    - 表示法使约束变得明确，从而可以轻松判断哪些移动是
        
        **非法的** (illegal)（如囚犯多于守卫）或**无效的** (unproductive)（如回到前一个状态）。
        
    - 通过系统地排除非法和无效移动，最终可以找到最优解（11步）。
        

**3.4 应用二：瑞文问题中的“表示与推理” (Represent & Reason for Raven's)**

- **核心思想**: 先用一种知识表示法（如语义网络）来表示问题，然后利用该表示进行推理，以解决问题 。
    
- **匹配与选择**:
    
    - 为 "A to B" 和 "C to an answer choice" 分别构建语义网络 。
        
    - 比较两个网络的变换关系是否匹配 。
        
    - **问题**: 当没有完全匹配的选项时，如何选择？
        
- **通过权重选择匹配 (Choosing Matches by Weights)**:
    
    - 为不同的变换类型（如
        
        `unchanged`, `deleted`, `scaled`, `rotation`, `reflection`）赋予不同的权重或分值，代表变换的“容易度”或“相似度” 。
        
    - 计算每种可能解释的总权重，选择权重最高的解释作为最佳答案 。
        
    - 这解决了歧义性问题，例如在“旋转”与“镜像”之间做出选择 。
        

**3.5 语义网络与其他概念的关联**

- **与认知科学的关联 (Cognitive Connection)**:
    
    - 语义网络与人类记忆的“扩散激活网络” (spreading activation networks) 理论相关 。
        
    - **示例**: 当听到 "John wanted to become rich. He got a gun." 时，大脑中相关概念节点被激活并扩散，连接路径上的节点（如 "rob a bank"）被纳入理解，从而完成故事的脑补 。
        
- **与KBAI三大过程的关联**:
    
    - **记忆 (Memory)**: 存储的案例（如 A to B 的关系）可以看作是记忆内容，新问题 (C to D) 是对记忆的探针 。
        
    - **推理 (Reasoning)**: 确定两个相似但不相同的情境中对象之间的对应关系（如A中的内圈对应C中的内三角）被称为**对应问题 (correspondence problem)**，这是类比推理的核心 。
        

---

### B. 文本思维导图 (Module 3)

- **Module 3: Semantic Networks**
    
    - **知识表示 (Knowledge Representation)**
        
        - _构成_:
            
            - **语言 (Language)** + 词汇
                
            - **内容 (Content)**
                
        - _特征_: 揭示关系，合适的抽象层级，完整、简洁、可计算
            
    - **语义网络 (Semantic Networks)**
        
        - _核心结构_:
            
            - _节点_: 代表对象
                
            - _带标签的链接_: 代表关系
                
        - _构建步骤 (瑞文问题为例)_:
            
            - 1. 为对象创建节点
                
            - 2. 链接节点表示内部关系 (
                
                `inside`, `above`)
                
            - 3. 链接不同网络的节点表示变换关系 (
                
                `unchanged`, `deleted`)
                
    - **应用与实践**
        
        - _守卫与囚犯问题_
            
            - _表示_:
                
                - 节点 = 状态 (State)
                    
                - 链接 = 移动 (Move)
                    
            - _推理_:
                
                - 在状态空间中寻找路径
                    
                - 排除
                    
                    **非法**和**无效**的移动
                    
        - _瑞文问题 (Represent & Reason)_
            
            - _过程_:
                
                - 1. 为
                    
                    `A->B` 和 `C->D` 分别创建语义网络
                    
                - 2. 比较两个网络的变换是否匹配
                    
            - _解决歧义：权重匹配_
                
                - _方法_: 为不同变换分配权重/分数
                    
                - _目的_: 计算总分，选择分数最高的解释作为答案
                    
    - **关联概念**
        
        - _KBAI三大过程_:
            
            - _记忆_: 存储的案例可被新问题检索
                
            - _推理_: 解决**对应问题 (correspondence problem)**
                
        - _认知科学_:
            
            - _关联理论_: 扩散激活网络 (Spreading Activation Networks)
                
            - _示例_: 通过激活扩散来理解不完整的短故事