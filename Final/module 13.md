### A. 结构化知识框架：Module 13 - Planning

**1. 规划 (Planning) 的定义与核心概念**

- **定义：** 规划是一种强大的动作选择 (Action Selection) 方法，智能体通过它将感知历史映射为动作 。
    
- **目标：** 解决“如何做动作选择”或“如何做操作符选择”的问题 。
    
- **逻辑基础：** 使用逻辑语法（命题逻辑）来设定目标、状态和操作符的规范 。
    
- **控制知识 (Control Knowledge)：** 知识不仅关于世界，还包含控制知识。目标 (Goals) 提供了控制知识，用于在不同操作符之间进行选择 。
    

**2. 规划系统的组成要素 (State, Goal, Operator)**

- **状态 (States)：**
    
    - **初始状态 (Initial State)：** 世界开始时的状态描述 (例如：`On(Robot, Floor) ∧ Dry(Ladder)`) 。
        
    - **目标状态 (Goal State)：** 期望达到的世界状态 (例如：`Painted(Ceiling) ∧ Painted(Ladder)`) 。
        
    - **完全指定 (Fully Specified)：** 需要同时指定初始状态和目标状态才能完全定义目标 。
        
- **操作符 (Operators)：**
    
    - **定义：** 现实世界中动作的心理表征 。
        
    - **前置条件 (Preconditions)：** 在应用操作符之前，世界中必须为真的断言。按照惯例，前置条件通常只包含正文字 (positive literals)，源自STRIPS规划器的传统 。
        
    - **后置条件 (Postconditions)：** 应用操作符之后，世界中变为真（或假）的断言 。后置条件可以包含否定文字（表示某事不再为真）。
        
    - **示例：** `climb-ladder` 操作符要求 `On(Robot, Floor)` 为真，执行后 `On(Robot, Ladder)` 为真 。
        

**3. 线性规划与冲突 (Linear Planning & Conflicts)**

- **手段-目的分析 (Means-Ends Analysis) 的局限：** 是一种启发式方法，可能会陷入死胡同，且无法保证最优性 。
    
- **线性规划器 (Linear Planner)：** 不尝试推理目标之间的冲突，只是像目标可以按任意顺序完成一样制定计划 。
    
- **目标破坏 (Goal Clobbering)：** 实现一个目标的计划可能会破坏 (clobber) 另一个目标的实现条件 。
    
    - **案例 (油漆天花板与梯子)：** 如果先画梯子 (`paint-ladder`)，梯子变湿 (`¬Dry(Ladder)`)，这就破坏了爬梯子 (`climb-ladder`) 的前置条件 (`Dry(Ladder)`)，从而无法画天花板 。
        

**4. 偏序规划 (Partial-Order Planning / Non-linear Planning)**

- **核心思想：** 一种避免多目标冲突的技术 。最初将目标视为相互独立，为每个目标生成部分计划，然后检测并解决冲突 。
    
- **冲突检测 (Detecting Conflicts)：**
    
    - 检查当前计划中操作符的前置条件是否被另一个计划中的某个状态破坏 。
        
    - 例如：`climb-ladder` 需要 `Dry(Ladder)`，但 `paint-ladder` 导致 `¬Dry(Ladder)`，这构成了冲突 。
        
- **冲突解决 (Resolving Conflicts)：**
    
    - 通过**提升 (Promote)** 或 **降低 (Demote)** 一个计划相对于另一个计划的顺序来解决冲突 。
        
    - 例如：必须先画天花板（提升该目标），再画梯子 。
        
- **开放前置条件 (Open Preconditions)：**
    
    - 当一个操作符的前置条件（如 `On(Robot, Floor)`）与当前状态（如 `On(Robot, Ladder)`）不匹配时，存在开放条件问题 。
        
    - **解决方法：** 选择一个新的操作符（如 `descend-ladder`）来满足这个条件 。
        
- **认知启示：** 偏序规划可以看作是三个简单代理（生成计划、检测冲突、解决冲突）交互产生的复杂行为，类似于明斯基的“心智社会 (Society of Mind)” 。
    

**5. 分层任务网络规划 (Hierarchical Task Network - HTN)**

- **背景：** 面对大规模复杂问题时，低级操作符会导致状态空间的组合爆炸 。
    
- **核心思想：** 在多个抽象层级上进行思考。将低级操作抽象为高级的**宏操作符 (Macro Operators)** 。
    
- **宏操作符 (Macro Operators)：**
    
    - 包含前置条件、后置条件以及**方法 (Method)** 。
        
    - **方法**描述了如何将宏操作符展开为低级的移动操作 。
        
    - **示例：** `unstack`（去堆叠）和 `stack-ascending`（按升序堆叠）概括了一系列具体的 `move` 操作 。
        
- **优势：** 使问题空间变小、更简单，易于导航 。
    

---

### B. 文本思维导图：Module 13 - Planning

- **Planning (规划)**
    
    - **定义：** 将感知历史映射为动作
        
    - **核心作用：** 动作选择 (Action Selection)
        
    - **基础组件 (基于逻辑)**
        
        - **State (状态)**
            
            - Initial State (初始状态)
                
            - Goal State (目标状态)
                
            - 表示法：命题逻辑 (e.g., `On(A, B)`)
                
        - **Operator (操作符)**
            
            - Preconditions (前置条件): 必须为真才能执行 (通常为正文字)
                
            - Postconditions (后置条件): 执行后变为真/假的状态
                
        - **Goal (目标)**
            
            - 提供控制知识 (Control Knowledge)
                
    - **Linear Planning (线性规划)**
        
        - 特点：按顺序解决目标，不推理冲突
            
        - **Goal Clobbering (目标破坏)**
            
            - 定义：一个目标的计划使另一个目标无法实现
                
            - 示例：先画梯子导致无法爬梯子去画天花板
                
    - **Partial-Order Planning (偏序规划/非线性规划)**
        
        - **流程**
            
            1. 独立为每个目标生成部分计划
                
            2. **Detect Conflicts (检测冲突)**
                
                - 检查前置条件是否被其他计划的状态破坏
                    
            3. **Resolve Conflicts (解决冲突)**
                
                - Promote (提升) 或 Demote (降低) 计划顺序
                    
            4. **Handle Open Preconditions (处理开放前置条件)**
                
                - 当前状态不满足条件时，插入新操作符 (e.g., `descend-ladder`)
                    
        - **认知关联**
            
            - Society of Mind (心智社会): 简单代理(生成、检测、解决)的交互
                
            - 使隐性的人类推理过程显性化
                
    - **Hierarchical Task Network (HTN) Planning (分层任务网络规划)**
        
        - **目的：** 解决复杂问题的组合爆炸
            
        - **方法：** 多层抽象 (Multiple levels of abstraction)
            
        - **Macro Operators (宏操作符)**
            
            - 包含：Preconditions, Postconditions, Method (展开规则)
                
            - 示例：Block World中的 `unstack`, `stack-ascending`