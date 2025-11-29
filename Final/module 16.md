### A. 结构化知识框架：Module 16 - Scripts

**1. 脚本 (Scripts) 的定义与核心功能**

- **定义：** 脚本是一种用于捕捉**因果连贯事件集 (causally coherent set of events)** 的知识表示形式 。
    
- **核心功能：**
    
    - 帮助智能体理解故事、话语和场景 。
        
    - 作为先前讨论的框架 (Frames)、理解 (Understanding) 和常识推理 (Common Sense Reasoning) 的集大成者 。
        
    - **生成期望 (Generating Expectations)：** 脚本能让智能体预测接下来会发生什么（自上而下的处理） 。
        
    - **检测惊奇 (Detecting Surprises)：** 当现实违反了脚本生成的期望时，就会产生惊奇 。
        

**2. 脚本的六大组成要素 (Parts of a Script)**

- **1. 进入条件 (Entry Conditions)：** 执行脚本所需的必要条件 (例如：顾客饿了且有钱) 。
    
- **2. 结果 (Result)：** 脚本执行后变为真的条件 (例如：顾客不再饿了，但钱少了；店主钱多了) 。
    
- **3. 道具 (Props)：** 执行脚本所涉及的物体 (例如：桌子、菜单、食物、支票) 。
    
- **4. 角色 (Roles)：** 参与脚本执行的代理 (例如：顾客、服务员、厨师、收银员) 。
    
- **5. 轨道 (Track)：** 特定脚本的变体或子类 (例如：“去餐厅”脚本可以有“咖啡馆”、“快餐”、“正式用餐”等轨道) 。
    
- **6. 场景 (Scenes)：** 脚本执行期间发生的事件序列 (例如：进入场景、点餐场景、进食场景) 。
    

**3. 脚本的构建与层级 (Construction & Hierarchy)**

- **宏观结构：** 脚本可以看作是由较小的知识结构（如 Frames/Primitive Actions）组成的“大分子” 。
    
- **场景展开：** 每个场景（如“进入”）可以进一步分解为一系列具体的动作帧（Action Frames），如移动身体、看、推断等 。
    
- **形式与内容 (Form vs. Content)：**
    
    - **形式：** 抽象的脚本定义（如一般的餐厅脚本）。
        
    - **内容：** 具体的实例化（如名为Salwa的机器人去Applebee's餐厅，服务员是Lucas） 。
        

**4. 脚本与其他AI方法的联系**

- **与规划 (Planning) 的关系：**
    
    - 脚本可以看作是**编译好的计划 (Compiled Plans)**。智能体不需要在运行时从头生成计划，而是直接从记忆中检索预存的脚本 。
        
    - 这解决了计算效率问题，因为检索比规划更快 。
        
- **与分类 (Classification) 的关系：**
    
    - 使用脚本的第一步通常是将当前情境**分类**到特定的脚本（如“这是快餐店”还是“这是正式餐厅”） 。
        
- **与学习 (Learning) 的关系：**
    
    - 脚本可以通过**增量概念学习 (Incremental Concept Learning)** 来习得（从经验中抽象出脚本） 。
        
    - 可以通过**基于解释的学习 (Explanation-Based Learning)** 或 **规划 (Planning)** 来生成脚本 。
        

**5. 认知连接 (Cognitive Connection)**

- **预测机器 (Predictive Machine)：** 大脑可以被视为预测机器，进行非常快速的自下而上处理，随后主要是自上而下的处理（基于脚本生成期望） 。
    
- **心理模型 (Mental Models)：** 脚本与心理模型的概念一致，不仅用于社交场合，也用于理解物理系统或经济运作 。
    
- **文化特异性 (Culture Specific)：** 脚本往往具有文化特异性（例如：在美国去餐厅通常包括给小费，而在某些国家则不然） 。
    

---

### B. 文本思维导图：Module 16 - Scripts

- **Scripts (脚本)**
    
    - **定义**
        
        - Causally coherent set of events (因果连贯的事件集)
            
        - 用于理解故事和常识推理
            
    - **核心功能**
        
        - Generate Expectations (生成期望)
            
        - Detect Surprises (检测惊奇/期望违背)
            
        - Infer Invisible Events (推断未提及的事件)
            
    - **六大要素 (Six Elements)**
        
        - **1. Entry Conditions (进入条件):** 前提 (e.g., Hungry, Has money)
            
        - **2. Result (结果):** 后果 (e.g., Less money, Not hungry)
            
        - **3. Props (道具):** 物体 (e.g., Tables, Menu)
            
        - **4. Roles (角色):** 代理 (e.g., Customer, Waiter)
            
        - **5. Track (轨道):** 变体 (e.g., Fast Food vs. Formal Dining)
            
        - **6. Scenes (场景):** 事件序列 (e.g., Entering, Ordering)
            
    - **操作流程**
        
        - **Retrieval (检索):** 类似于分类问题，根据情境选择脚本
            
        - **Instantiation (实例化):** 将具体变量填入脚本的形式中
            
        - **Execution (执行):** 遵循脚本步骤，无需实时规划
            
    - **与其他方法的关系**
        
        - **Frames:** 脚本由 Frame 组成 (Molecules of knowledge)
            
        - **Planning:** 脚本是 Pre-stored/Compiled Plans (预存/编译的计划)
            
        - **Learning:** 通过 Incremental Concept Learning 或 Planning 习得
            
    - **Cognitive Connection (认知联系)**
        
        - 大脑作为预测机器 (Predictive Machine)
            
        - 自上而下的处理 (Top-down processing)
            
        - 文化特异性 (Culture Specificity)