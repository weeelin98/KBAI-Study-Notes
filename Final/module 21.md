### A. 结构化知识框架：Module 21 - Configuration

**1. 核心定义与背景 (Definition & Context)**

- **设计 (Design) 的定义：**
    
    - **输入：** 需求、目标或功能 (Needs, Goals, Functions)。
        
    - **输出：** 满足上述需求的工件 (Artifact) 结构的规范。
        
    - **特点：** 开放式 (Open-ended)、定义不明确 (Ill-defined)。在设计中，问题和解决方案是**协同进化 (Co-evolve)** 的，即随着解决方案的发展，对问题的理解也在演变 。
        
- **配置 (Configuration) 的定义：**
    
    - 配置是一种**常规设计 (Routine Design)** 任务 。
        
    - **关键特征：**
        
        - 所有组件 (Components) 都是**已知**的 。
            
        - 任务是为组件的变量**赋值 (Assign Values)**，并根据约束 (Constraints) 对其进行**排列 (Arrange)** 。
            
    - **示例：** 房间家具摆放、飞机座椅布局、相机参数设置、地下室设计 。
        

**2. 配置过程与方法 (The Configuration Process)**

- **计划细化 (Plan Refinement) 方法：**
    
    - **抽象层次 (Abstraction Hierarchy)：** 使用抽象层级来组织计划 。
        
    - **流程步骤：**
        
        1. **抽象计划 (Abstract Plan)：** 从高层计划开始，该计划指定了变量的一个子集。
            
        2. **赋值 (Assign Values)：** 为当前计划层级的变量赋值。
            
        3. **细化与扩展 (Refine and Expand)：** 将完成的计划细化为更低层级的计划（例如，从“房子”细化为“地下室”、“主楼层”）。
            
        4. **迭代 (Iterate)：** 重复上述过程，直到形成完整的排列模型 。
            
- **处理约束 (Handling Constraints)：**
    
    - **输入规范：** 包含必须满足的约束（如：椅子成本 < $20, 重量 > 200g）。
        
    - **启发式 (Heuristics)：** 使用经验法则来指导变量赋值顺序（例如：先决定最受限的变量，或先决定最重要的变量，如成本）。
        
    - **冲突解决：** 如果生成的解决方案不满足约束，需要迭代过程（调整赋值）或更改规范（如果允许）。
        

**3. 案例分析：椅子设计 (Example: Chair Configuration)**

- **知识表示 (Representation)：** 使用 **框架 (Frame)** 表示椅子的原型知识 。
    
    - **组件 (Slots)：** 腿 (Legs)、座 (Seat)、背 (Back)、扶手 (Arms)。
        
    - **变量 (Variables)：** 尺寸 (Size/Mass)、材料 (Material)、成本 (Cost)、数量 (Count)。
        
    - **取值范围 (Ranges)：** 每个变量都有预定义的值域（例如：座的质量 10-100g）。
        
- **推理过程：**
    
    1. 列出所有约束。
        
    2. 应用抽象计划（例如：先分配成本）。
        
    3. 细化组件（例如：确定腿的数量、材料、质量）。
        
    4. 计算总属性（总质量、总成本）以验证是否满足约束 。
        

**4. 配置与其他 AI 主题的联系 (Connections)**

- **与分类 (Classification) 的联系：**
    
    - **区别：** 分类用于**理解**世界（将感知映射到类），配置用于**创造**世界（设计动作或结构）。
        
    - **联系：** 配置利用了分类中的“原型概念” (Prototypical Concepts) 和“建立-细化” (Establish-Refine) 的逻辑 。
        
- **与基于案例推理 (CBR) 的联系：**
    
    - 两者都用于常规设计。
        
    - **配置：** 从抽象原型/计划开始，通过赋值进行实例化 。
        
    - **CBR：** 从具体的旧设计（案例）开始，通过调整 (Tweaking) 来适应新问题 。
        
- **与规划 (Planning) 的联系：**
    
    - 配置可以看作是一种规划，其中计划是预先存在的（骨架计划 Skeletal Plan），任务是实例化这些计划 。
        
- **与约束传播 (Constraint Propagation) 的联系：**
    
    - 配置是约束传播的一种形式，通过变量赋值来满足某些条件 。
        

---

### B. 文本思维导图：Module 21 - Configuration

- **Configuration (配置)**
    
    - **定义 (Definition)**
        
        - Routine Design (常规设计)
            
        - Components Known (组件已知)
            
        - Task: Assign Values & Arrange (任务：赋值与排列)
            
    - **Design Context (设计背景)**
        
        - Problem & Solution Co-evolution (问题与解协同进化)
            
        - Ill-defined & Open-ended (定义不清与开放式)
            
    - **Process: Plan Refinement (过程：计划细化)**
        
        - **Steps (步骤)**
            
            - 1. Abstract Plan (抽象计划)
                    
            - 2. Assign Values (赋值)
                    
            - 3. Refine & Expand (细化与扩展)
                    
            - 4. Iterate (迭代)
                    
        - **Key Elements (关键要素)**
            
            - Variables (变量) & Ranges (值域)
                
            - Constraints (约束) (e.g., Cost, Mass)
                
            - Heuristics (启发式) (e.g., most restricted first)
                
    - **Example: Chair Design (案例：椅子)**
        
        - **Representation:** Frames (框架)
            
        - **Components:** Legs, Seat, Back, Arms
            
        - **Variables:** Material, Mass, Cost
            
        - **Action:** 满足 "Cost < $20" 等约束
            
    - **Connections (联系)**
        
        - vs. Classification: Create (创造) vs. Make Sense (理解)
            
        - vs. CBR: Abstract Plan (抽象计划) vs. Specific Case (具体案例)
            
        - vs. Planning: Instantiation of skeletal plans (骨架计划的实例化)
            
        - vs. Constraint Propagation: A specific instance of it (特定实例)