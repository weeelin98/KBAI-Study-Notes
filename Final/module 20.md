### A. 结构化知识框架：Module 20 - Constraint Propagation

**1. 核心定义与目标**

- **定义：** 约束传播是一种推理机制，它为刻画问题的变量分配值 (Values)，以满足特定的条件，这些条件被称为**约束 (Constraints)** 。
    
- **通用性：** 它是一种非常通用的方法，不仅用于独立的推理，还广泛应用于规划 (Planning)、理解 (Understanding)、自然语言处理 (NLP) 和视觉空间推理 (Visuospatial Reasoning) 等领域 。
    

**2. 应用案例 I：计算机视觉与线条标记 (Computer Vision & Line Labeling)**

- **任务目标：** 从二维 (2D) 图像中识别三维 (3D) 物体（例如从线条图中识别立方体）。
    
- **Marr的视觉理论 (David Marr's Theory)：**
    
    1. 检测边缘/线条 (Edges/Lines) 。
        
    2. 将线条分组为表面 (Surfaces) 并确定方向 。
        
    3. 将表面组合成完整的3D对象 。
        
- **线条标记 (Line Labeling) 流程：**
    
    - **变量 (Variables)：** 线条 (Edges)。
        
    - **值 (Values)：** 线条的属性，如 **折痕 (Fold)**（两条表面相交形成的线）或 **刀锋 (Blade)**（一条表面遮挡另一条表面形成的线）。
        
    - **约束来源 (Junctions)：** 三面体物体（如立方体）的顶点形成的连接点形状：
        
        - **Y型连接 (Y-Junction)：** 约束为三条线都是折痕 (Fold, Fold, Fold) 。
            
        - **L型连接 (L-Junction)：** 约束为 (Blade, Blade) 或 (Blade, Fold) 。
            
        - **W型连接 (W-Junction)：** 约束为 (Blade, Fold, Blade) 。
            
    - **传播机制：** 如果一条线在一个连接点被确定为“折痕”，那么这条线连接到下一个连接点时，必须保持“折痕”的属性，从而限制了下一个连接点的可能性 。
        

**3. 应用案例 II：自然语言处理 (Natural Language Processing)**

- **任务目标：** 确定句子的语法正确性（即使语义无意义）。
    
    - _示例句子：_ "Colorless green ideas sleep furiously"（无色的绿色思想愤怒地睡觉）—— 语义不通但语法正确 。
        
- **约束传播流程：**
    
    - **变量 (Variables)：** 句子中的单词 。
        
    - **值 (Values)：** 词性类别（如名词、动词、形容词）。
        
    - **约束 (Constraints)：** 语法规则 (Grammar Rules)。
        
        - 例如：句子 -> 名词短语 + 动词短语；名词短语 -> 形容词 + 名词 。
            
    - **过程：** 为单词分配词性，看是否能构建出满足所有语法规则的解析树 (Parse Tree) 。如果能满足所有约束，则句子语法正确。
        

**4. 高级问题与挑战 (Advanced Issues)**

- **歧义性 (Ambiguity)：**
    
    - 有时多种解释都能同时满足所有约束。
        
    - _视觉示例：_ 一个线条图既可以看作是从外部看建筑物，也可以看作是从内部看盒子 。
        
    - _语言示例：_ 双关语 (Puns)，一个词同时满足两种解释的约束 。
        
- **复杂本体论 (Complex Ontology)：**
    
    - 对于复杂的场景（如物体遮挡），简单的约束（如Y型连接只能是全折痕）是不够的。需要引入更复杂的约束集（如Y型也可以是全刀锋）。
        
    - **解决方法：** 引入额外约定，例如“背景边缘总是刀锋 (Blades)”，以帮助消除歧义 。
        

**5. 认知连接 (Cognitive Connection)**

- **通用机制：** 约束传播是人类认知中的核心过程，用于利用世界知识来理解感知数据 。
    
- **类型：**
    
    - **符号约束 (Symbolic Constraints)：** 如上述的视觉和语言规则。
        
    - **数值约束 (Numerical Constraints)：** 如Excel电子表格中的公式传播 。
        

---

### B. 文本思维导图：Module 20 - Constraint Propagation

- **Constraint Propagation (约束传播)**
    
    - **定义**
        
        - Assign values to variables (为变量赋值)
            
        - Satisfy conditions/constraints (满足条件/约束)
            
    - **Computer Vision Application (计算机视觉应用)**
        
        - **Task:** 3D Object Recognition from 2D drawings (三维物体识别)
            
        - **Marr's Approach:** Edges -> Surfaces/Orientations -> 3D Object
            
        - **Line Labeling (线条标记)**
            
            - **Variables:** Lines (线条)
                
            - **Values:** Folds (折痕), Blades (刀锋)
                
            - **Constraints (Junction Types):**
                
                - Y-Junction: Fold-Fold-Fold (or Blade-Blade-Blade)
                    
                - L-Junction: Blade-Blade (or Blade-Fold)
                    
                - W-Junction: Blade-Fold-Blade
                    
            - **Process:** Propagate labels from one junction to the next
                
    - **Natural Language Application (自然语言应用)**
        
        - **Task:** Grammatical Correctness Check (语法正确性检查)
            
        - **Example:** "Colorless green ideas sleep furiously"
            
        - **Components:**
            
            - **Variables:** Words (单词)
                
            - **Values:** Lexical categories (Noun, Verb, etc.)
                
            - **Constraints:** Grammar rules (语法规则)
                
    - **Advanced Issues (高级问题)**
        
        - **Ambiguity (歧义):** Multiple valid interpretations (e.g., Puns, Necker cube)
            
        - **Complex Ontology:** Need for richer constraints in occlusion scenes
            
        - **Conventions:** Using heuristics (e.g., "background edges are blades") to resolve ambiguity
            
    - **Cognitive Connection (认知联系)**
        
        - General purpose method (通用方法)
            
        - Symbolic vs. Numerical constraints (符号与数值约束)