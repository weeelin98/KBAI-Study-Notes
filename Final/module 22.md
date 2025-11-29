### A. 结构化知识框架：Module 22 - Diagnosis

**1. 核心定义与背景 (Definition & Context)**

- **诊断 (Diagnosis) 的定义：**
    
    - 识别导致系统故障的**故障 (Faults)**。
        
    - **系统 (System)** 可以是汽车、计算机程序、生物体（医学诊断）或经济体。
        
- **诊断的触发 (Trigger)：**
    
    - **预期行为 (Expected Behavior)** 与 **观察行为 (Observed Behavior)** 之间存在**差异 (Discrepancy)**。
        
    - 这种差异表明系统存在故障 (Malfunction)。
        
- **领域示例：**
    
    - **汽车引擎：** 预期转动但没转 -> 检查化油器或火花塞。
        
    - **计算机硬件：** 预期低温运行但过热 -> 风扇故障。
        
    - **软件调试：** “橡皮鸭调试法” (Rubber duck debugging) —— 通过解释代码模型来发现错误。
        

**2. 诊断过程：空间映射 (Data & Hypothesis Spaces)**

- **两个空间：**
    
    - **数据空间 (Data Space)：** 关于故障系统的观察数据（例如：体温104度，A升高，C降低）。
        
    - **假设空间 (Hypothesis Space)：** 能够解释数据的故障假设（例如：流感，化油器坏了）。
        
- **映射过程 (Mapping)：** 诊断就是构建从数据空间到假设空间的映射。
    
- **启发式分类 (Heuristic Classification) 方法：**
    
    1. **数据抽象 (Data Abstraction)：** 将具体数据（体温104度）抽象为一般特征（高烧）。这是自下而上的分类。
        
    2. **映射 (Mapping)：** 将抽象数据映射到抽象假设（高烧 -> 感染）。
        
    3. **假设细化 (Hypothesis Refinement)：** 将抽象假设细化为具体故障（感染 -> 流感）。这是自上而下的分类。
        

**3. 诊断的复杂性与挑战 (Problems/Complexity)**

- **多对多映射：**
    
    - 一个数据点可由多个假设解释（发烧可能是流感，也可能是感染）。
        
    - 一个假设可解释多个数据点（流感导致发烧、疲劳、发抖）。
        
- **假设间的相互作用 (Interactions)：**
    
    - **互斥 (Mutual Exclusion)：** 假设A存在则假设B不可能存在。
        
    - **抵消 (Cancellation)：** 两个假设的效果相互抵消，导致症状消失（例如：流感导致体温升高 + 免疫力低下导致体温降低 = 体温正常）。这使得诊断非常困难。
        

**4. 诊断的推理逻辑：溯因推理 (Abduction)**

- **三种推理类型的比较：**
    
    - **演绎 (Deduction)：** 规则 + 原因 -> 结果。 (保真：如果前提为真，结论必为真)。
        
        - _例：_ 如果流感则发烧 + 有流感 -> 必然发烧。
            
    - **归纳 (Induction)：** 原因 + 结果 -> 规则。 (不保真：从样本推广到整体)。
        
        - _例：_ 看到多次流感伴随发烧 -> 归纳出“如果流感则发烧”的规则。
            
    - **溯因 (Abduction)：** 规则 + 结果 -> 原因。 (不保真：可能有其他原因)。
        
        - _例：_ 如果流感则发烧 + 发烧 -> 推测可能是流感。
            
- **诊断本质：** 诊断是溯因推理的一个实例 (Diagnosis is an instance of abduction)。
    
- **科学循环：** 观察数据 -> **溯因**解释 -> **归纳**规则 -> **演绎**预测 -> 观察更多数据。
    

**5. 假设选择标准 (Criteria for Choosing a Hypothesis)**

- 当有多个竞争假设时，如何选择？
    
    1. **解释覆盖率 (Explanatory Coverage)：** 选择能解释最多数据点的假设。
        
    2. **简约性 (Parsimony / Occam's Razor)：** 选择最简单的假设（例如，单个疾病比三个并发疾病更优，除非数据强迫选择后者）。
        
    3. **置信度 (Confidence / Priors)：** 选择先验概率更高、更有信心的假设（例如，常见病优于罕见病）。
        
- **平衡：** 诊断往往是在这三个标准之间进行权衡。
    

**6. 完成诊断流程 (Completing the Process)**

- **从假设到治疗 (Treatment)：**
    
    - 一旦确定假设，就将其作为索引进入**治疗空间 (Treatment Space)**（例如：流感 -> 休息/药物）。
        
    - 这也是一种**配置 (Configuration)** 任务：配置一个治疗方案来修复故障。
        
- **监控与迭代：**
    
    - 执行治疗后需要监控结果。
        
    - 如果治疗失败，这本身就是新的数据，需要重新开始诊断循环（收集更多数据，修正假设）。
        

---

### B. 文本思维导图：Module 22 - Diagnosis

- **Diagnosis (诊断)**
    
    - **定义**
        
        - Identification of faults (识别故障)
            
        - Trigger: Discrepancy between Expected & Observed Behavior (预期与观察行为的差异)
            
    - **Process Model (过程模型)**
        
        - **Spaces (空间)**
            
            - Data Space (数据空间): Observations, Symptoms
                
            - Hypothesis Space (假设空间): Faults, Diseases
                
        - **Mapping (映射)**
            
            - Heuristic Classification (启发式分类)
                
                - Bottom-up: Data Abstraction
                    
                - Mapping: Abstract Data -> Abstract Hypothesis
                    
                - Top-down: Hypothesis Refinement
                    
    - **Complexity Factors (复杂性因素)**
        
        - M-to-N Mapping (多对多映射)
            
        - **Interactions (相互作用)**
            
            - Mutual Exclusion (互斥)
                
            - Cancellation (抵消)
                
    - **Inference Type: Abduction (溯因推理)**
        
        - Rule + Effect -> Cause
            
        - Not truth-preserving (不保真)
            
        - Contrast with:
            
            - Deduction (Rule + Cause -> Effect)
                
            - Induction (Cause + Effect -> Rule)
                
    - **Hypothesis Selection Criteria (假设选择标准)**
        
        - 1. Explanatory Coverage (解释覆盖率)
                
        - 2. Parsimony (简约性/奥卡姆剃刀)
                
        - 3. Confidence/Priors (置信度/先验概率)
                
    - **Post-Diagnosis (诊断后)**
        
        - Map to Treatment Space (映射到治疗空间)
            
        - Monitor & Iterate (监控与迭代)
            
            - Treatment failure = New data
                
    - **Connections (联系)**
        
        - vs. Classification (分类): 诊断包含分类
            
        - vs. Configuration (配置): 治疗方案生成是配置任务
            
        - Cognitive Connection: 处理期望违背 (Expectation Violation)