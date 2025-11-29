### A. 结构化知识框架：Module 18 - Analogical Reasoning

**1. 核心定义与目标 (Definition & Goals)**

- **定义：** 类比推理通过**问题族 (Family of problems)** 来理解新问题，并通过跨域 (Cross-domain) 迁移已知问题的关系知识来解决新问题 。
    
- **核心特征：** 涉及跨领域的知识迁移，即**源案例 (Source Case)** 和 **目标问题 (Target Problem)** 来自不同的领域 。
    

**2. 相似性 (Similarity)**

- **相似性谱系 (Spectrum of Similarity)：**
    
    - **记录案例 (Recording Cases)：** 关系、对象、特征、值均相同（完全匹配）。
        
    - **基于案例推理 (CBR)：** 关系和对象相同，但特征值不同（域内类比）。
        
    - **类比推理 (Analogical Reasoning)：** 仅**关系 (Relationships)** 相似，对象和特征可能完全不同（跨域类比）。
        
- **相似性的三个维度 (Types of Similarity)：**
    
    1. **语义相似性 (Semantic)：** 概念上的相似（例如：女人爬梯子 vs. 女人爬折梯）。
        
    2. **语用相似性 (Pragmatic)：** 外部因素（如目标）的相似（例如：攻占堡垒 vs. 治疗肿瘤）。
        
    3. **结构相似性 (Structural)：** 表征结构（关系图）的相似，而非物理结构 。
        
- **深层 vs. 表层相似性：**
    
    - **表层 (Superficial)：** 对象、特征、计数的相似 。
        
    - **深层 (Deep)：** 对象间**关系**的相似，尤其是高阶关系（关系之间的关系）。
        

**3. 类比推理的五阶段流程 (The Process)**

1. **检索 (Retrieval)：** 从记忆中找到与目标问题具有深层相似性的源案例 。
    
2. **映射 (Mapping)：** 解决**对应问题 (Correspondence Problem)**，确定目标中的哪个对象对应源中的哪个对象 。
    
    - _策略：_ 优先利用高阶关系进行对齐 。
        
3. **迁移 (Transfer)：** 将源案例中的解决方案或策略（通常是抽象的因果模式）迁移到目标问题 。
    
4. **评估 (Evaluation)：** 验证提出的解决方案是否有效（例如通过模拟）。
    
5. **存储 (Storage)：** 将新问题及其解决方案封装为新案例存入记忆 。
    

**4. 经典案例分析**

- **Duncker 辐射问题 (The Duncker Radiation Problem)：**
    
    - **目标问题：** 医生用激光治疗肿瘤，强光会杀死健康组织 。
        
    - **源案例：** 军队攻占堡垒，大部队会引爆地雷 。
        
    - **映射与迁移：**
        
        - 医生 <-> 将军；激光 <-> 军队；肿瘤 <-> 堡垒。
            
        - 策略：**分解 (Decompose)** 资源（分散小股部队/分散弱激光束），从不同方向同时汇聚到目标 。
            
- **太阳系与原子结构：**
    
    - 利用太阳系模型理解原子结构。
        
    - **深层相似性：** 都有“围绕旋转”、“吸引力”等关系，尽管对象完全不同 。
        

**5. 基于类比的设计 (Design by Analogy)**

- **生物仿生 (Biomimicry)：**
    
    - **案例 1 (Basilisk Lizard)：** 设计水上行走机器人。检索到一种能水上行走的蜥蜴，迁移其脚部结构和行为模式 。
        
    - **案例 2 (Microbot)：** 设计隐身潜水微型机器人。
        
        - 低速游动：类比桡足类动物 (Copepod) 。
            
        - 高速游动：类比乌贼 (Squid) (喷射推进) 。
            
        - **复合类比 (Compound Analogy)：** 结合多个源案例的部分来解决一个复杂问题 。
            

**6. 高级与开放问题 (Advanced Issues)**

- **共同词汇 (Common Vocabulary)：** 跨域映射是否需要统一的词汇表？（如 revolve vs. rotate）。
    
- **问题抽象 (Problem Abstraction)：** 为了检索，往往需要先对问题进行抽象 。
    
- **复合与组合类比 (Compound & Compositional Analogy)：** 多源案例结合，或多层级抽象（人、过程、组织）的类比 。
    

---

### B. 文本思维导图：Module 18 - Analogical Reasoning

- **Analogical Reasoning (类比推理)**
    
    - **Definition:** Cross-domain knowledge transfer (跨域知识迁移)
        
    - **Similarity (相似性)**
        
        - **Spectrum (谱系):**
            
            - Recording Cases (Identical) -> CBR (Same Domain) -> Analogy (Cross Domain)
                
        - **Types (类型):**
            
            - Semantic (Conceptual)
                
            - Pragmatic (Goals/External)
                
            - Structural (Representational relationships)
                
        - **Deep vs. Superficial:** Focus on _Relationships_ (especially higher-order) over Objects/Features
            
    - **The Process (流程)**
        
        - **1. Retrieval:** Finding the source case
            
        - 2. Mapping: Alignment/Correspondence (e.g., General -> Doctor)
            
        - 3. Transfer: Importing the strategy/pattern
            
        - 4. Evaluation: Simulation/Testing
            
        - 5. Storage: Incremental learning
            
    - **Examples (案例)**
        
        - **Medical/Fortress:** Decomposition strategy
            
        - **Solar System/Atom:** Structural similarity (Attraction, Revolution)
            
    - **Design by Analogy (基于类比的设计)**
        
        - **Biomimicry:** Robot walking on water <-> Basilisk Lizard
            
        - **Compound Analogy:** Microbot <-> Copepod + Squid
            
    - **Cognitive Connection**
        
        - Metaphors (隐喻)
            
        - Raven's Test (瑞文测试)