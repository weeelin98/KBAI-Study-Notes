### A. 结构化知识框架：Module 26 - Wrap-Up

**1. 认知系统架构再探 (Cognitive Systems Revisited)**

- **三层空间 (Three Spaces)：** 这种架构不仅用于构建 AI 代理，也用于反思人类认知 。
    
    - **反应空间 (Reactive Space)：** 直接将环境中的感知 (Percepts) 映射为动作 (Actions)（“看-动”循环）。
        
    - **审思空间 (Deliberative Space)：** 将感知映射为动作，但过程由**推理**、**学习**和**记忆**介导（“看-想-动”循环）。
        
    - **元认知空间 (Metacognitive Space)：** 位于内部世界，监控审思推理，对内部思维、学习和推理进行操作 。
        
- **与世界的交互：**
    
    - 认知系统不仅处于物理世界，也处于**社会世界 (Social World)**，与其他认知系统交互 。
        
    - 输入持续不断（感知、目标、信号），输出持续不断（动作、计划、内部知识更新） 。
        

**2. KBAI 的七大核心原则 (The 7 Principles of KBAI)** 这是课程的理论基石，概括了知识型 AI 的核心特征：

- **原则 1：表示与组织 (Represent & Organize)**
    
    - 知识型 AI 代理将知识表示并组织成**知识结构 (Knowledge Structures)**，以指导和支持推理 。
        
    - _核心范式：_ 表示与推理 (Represent and Reason) 。
        
    - _案例：_ 语义网络、框架 (Frames)、脚本 (Scripts) 。
        
- **原则 2：增量学习 (Learning is Incremental)**
    
    - 学习往往是增量的，信息、数据或经验**逐个到达 (Arrive one at a time)** 。
        
    - _案例：_ 记录案例学习、增量概念学习、版本空间、纠错学习 。
        
- **原则 3：自上而下与自下而上的处理 (Top-down & Bottom-up)**
    
    - 推理不仅是自下而上（数据驱动），也是**自上而下 (Top-down)** 的 。
        
    - 低级处理激活记忆中的知识结构，这些结构生成**期望 (Expectations)**，从而指导后续处理 。
        
    - _案例：_ 框架生成槽位期望、脚本预测下一事件、约束传播 。
        
- **原则 4：方法匹配任务 (Match Methods to Tasks)**
    
    - 知识型 AI 代理根据任务特性选择合适的方法 。
        
    - 方法与任务的区别不是绝对的，方法可以生成子任务 。
        
    - _案例：_ 配置任务可用“生成与测试”或“问题归约”；元推理负责策略选择 。
        
- **原则 5：启发式与满意解 (Heuristics & Satisficing)**
    
    - AI 代理使用**启发式 (Heuristics)** 来寻找**足够好 (Good enough/Satisficing)** 的解，而不是追求最优解 。
        
    - _权衡：_ 计算效率 vs. 解的最优性。解决有限理性与计算难解性的矛盾 。
        
    - _案例：_ 手段-目的分析、增量概念学习中的“必须连接”启发式 。
        
- **原则 6：利用重复模式 (Recurring Patterns)**
    
    - AI 代理利用问题中**重复出现的模式**来解决问题 。
        
    - 即便面对新问题，底层模式往往与旧经验相似 。
        
    - _案例：_ 记录案例学习、基于案例推理 (CBR)、类比推理（跨域模式迁移） 。
        
- **原则 7：统一架构 (Unified Architecture)**
    
    - 知识型 AI 代理的架构使推理、学习和记忆相互支持和约束 。
        
    - **知识 (Knowledge)** 是连接这三者的胶水 。
        
    - _案例：_ 产生式系统（推理僵局 -> 记忆提供情景 -> 学习分块规则 -> 解决僵局） 。
        

**3. 课程主题回顾 (Course Topic Revisited)**

- **基础 (Fundamentals):** 语义网络、生成与测试、手段-目的分析、问题归约、产生式系统 。
    
- **规划 (Planning):** 逻辑、线性规划、偏序规划、分层规划 。
    
- **常识推理 (Common Sense):** 框架、理解、常识推理、脚本 。
    
- **学习 (Learning):** 记录案例、增量概念学习、版本空间、纠错学习 。
    
- **类比与视觉 (Analogical & Visuospatial):** 类比推理（检索/映射/迁移）、约束传播、视觉空间推理 。
    
- **设计与元认知 (Design & Metacognition):** 配置、诊断、设计、创造力、元推理、伦理 。
    

**4. 当前研究项目 (Current Research)**

- **CALO:** 认知助手（Siri的前身） 。
    
- **Cyc & OMCS:** 大规模常识知识库 。
    
- **Wolfram Alpha:** 基于结构化知识的计算引擎 。
    
- **VITA:** 自闭症视觉思维模型（解决瑞文测试） 。
    
- **Dramatis:** 故事悬念模型 。
    
- **DANE:** 生物学类比设计支持系统 。
    

---

### B. 文本思维导图：Module 26 - Wrap-Up

- **Wrap-Up (课程总结)**
    
    - **Cognitive Architecture (认知架构)**
        
        - **Layers (层级):**
            
            - Reactive (反应层): Percept -> Action
                
            - Deliberative (审思层): Reason + Learn + Memory
                
            - Metacognitive (元认知层): Thinking about thinking
                
        - **Context:** Situated in Physical & Social World
            
    - **The 7 Principles (七大原则)**
        
        - 1. **Represent & Organize:** Knowledge structures guide reasoning
            
        - 2. **Incremental Learning:** Data arrives one at a time
            
        - 3. **Top-down & Bottom-up:** Expectations drive reasoning
            
        - 4. **Match Methods to Tasks:** Selection based on problem type
            
        - 5. **Heuristics & Satisficing:** Good enough solutions for efficiency
            
        - 6. **Recurring Patterns:** Reuse old solutions/patterns
            
        - 7. **Unified Architecture:** Reasoning, Learning, Memory constrain each other
            
    - **Topic Integration (主题整合)**
        
        - Fundamentals -> Planning -> Common Sense -> Learning -> Analogical -> Visuospatial -> Design -> Metacognition
            
    - **Research Frontiers (研究前沿)**
        
        - Assistants (CALO)
            
        - Common Sense Bases (Cyc, OMCS)
            
        - Visual Thinking (VITA)
            
        - Creativity/Story (Dramatis)
            
        - Design (DANE)