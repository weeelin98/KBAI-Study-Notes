### A. 结构化知识框架：Module 15 - Commonsense Reasoning

**1. 核心定义与目标 (Definition & Goals)**

- **定义：** 常识推理是指做出关于世界的自然、显而易见的推论的能力 。
    
- **目标：** 帮助 AI 智能体像人类一样，利用常识避免做出愚蠢的决定（例如：为了查看天气是否下雨而跳出窗户） 。
    
- **挑战：** 自然语言中存在大量词汇表达相似含义（如 ate, devoured, consumed, ingested），机器需要理解它们在深层含义上是相同的 。
    

**2. 核心机制：原语动作 (Primitive Actions)**

- **概念：** Schank 提出了一组少量的（约14个）原语动作，可以覆盖英语中的大部分动词含义 。
    
- **作用：** 将表面上不同的句子（如 "Ashok ate a frog" 和 "Ashok inhaled a frog"）映射到同一个内部表示（**Ingest**），从而实现统一的推理 。
    
- 主要的 14 个原语动作 ：
    
    - **物理动作：** `Move-body-part` (移动身体部位), `Expel` (排出), `Propel` (推进/施力), `Move-object` (移动物体), `Ingest` (摄入).
        
    - **感官动作：** `See` (看), `Smell` (闻), `Hear` (听), `Feel` (感觉).
        
    - **抽象/社交动作：** `Move-possession` (所有权转移), `Think-about` (思考), `Speak` (说), `Move-concept` (概念转移), `Conclude` (结论).
        

**3. 动作框架与处理流程 (Action Frames & Processing)**

- **框架结构：** 每个原语动作都有一个对应的框架，包含特定的槽位（Slots），如 `Agent` (代理), `Object` (对象), `Instrument` (工具), `Destination` (目的地) 等 。
    
- **自上而下的处理 (Top-Down Processing)：**
    
    1. 识别句子中的动词（如 "ate"）。
        
    2. 检索对应的原语动作框架（如 `Ingest`）。
        
    3. 利用框架的预期来从句子中提取信息填充槽位（如 Agent=Ashok, Object=Frog） 。
        

**4. 复杂情况的处理 (Handling Complexities)**

- **隐含动作 (Implied Actions)：**
    
    - 有些动词不能直接映射到原语，而是暗示了一个动作。
        
    - _示例：_ "John fertilized the field" (约翰给田地施肥) -> 暗示 "John **put** fertilizer on the field" (约翰把肥料放在田地里) -> 映射为 `Move-object` 。
        
    - _示例：_ "Bill shot Bob" (比尔射击鲍勃) -> 暗示 "Bill **propelled** a bullet into Bob" (比尔推进一颗子弹进入鲍勃) 。
        
- **状态变化 (State Changes)：**
    
    - 动作会导致状态的改变。框架中通常包含 `Result` 槽位来捕捉这种变化。
        
    - _示例：_ "Ashok enjoyed eating the frog"。这里有两个框架：
        
        1. `Ingest` (吃青蛙)。
            
        2. `State-Change` (Ashok的心情变得快乐)，这是 `Ingest` 的结果 。
            
- **通用动作 (Generic Action - Do)：**
    
    - 当无法确定具体原语时，使用通用的 `Do`。
        
    - _示例：_ "Susan comforted Jing" -> Susan **Did** something that resulted in Jing becoming happy 。
        

**5. 认知连接 (The Cognitive Connection)**

- **避免愚蠢行为：** 我们不跳窗查天气，是因为常识推理告诉我们这会导致受伤（状态改变），这违背了生存目标 。
    
- **心智理论 (Theory of Mind)：** 在社交世界中，我们将目标、信念和欲望归因于他人，从而预测和理解他人的行为 。
    

---

### B. 文本思维导图：Module 15 - Commonsense Reasoning

- **Commonsense Reasoning (常识推理)**
    
    - **Goal:** Make natural inferences, avoid stupid actions (e.g., jumping out of window)
        
    - **Core Tool:** Primitive Actions (原语动作)
        
        - **Physical:** `Ingest`, `Propel`, `Move-object`, `Move-body-part`, `Expel`
            
        - **Sensory:** `See`, `Smell`, `Hear`, `Feel`
            
        - **Abstract/Social:** `Speak`, `Move-possession`, `Move-concept`, `Think-about`, `Conclude`
            
    - **Representation: Action Frames (动作框架)**
        
        - Slots: Agent, Object, Destination, Instrument
            
        - Process: Verb -> Retrieve Frame -> Fill Slots (Top-down)
            
    - **Advanced Handling (高级处理)**
        
        - **Implied Actions (隐含动作):**
            
            - "Fertilized" -> "Put fertilizer" (`Move-object`)
                
            - "Shot" -> "Propelled bullet" (`Propel`)
                
        - **State Changes (状态改变):**
            
            - Result of actions (e.g., `Ingest` -> Not Hungry/Happy)
                
        - **Ambiguity (歧义):** "Enjoyed eating" -> `Feel` + `Ingest`
            
        - **Generic Action:** `Do` (used when specific primitive is unclear)
            
    - **Cognitive Connection**
        
        - Using context/goals to decide actions
            
        - **Theory of Mind:** Ascribing goals/beliefs to others