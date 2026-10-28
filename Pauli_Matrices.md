### 1. ข้อมูลดิบจากการวัด (The Observables & Eigenvalues)

**ผลการทดลอง:** เมื่อยิงอิเล็กตรอนผ่านเครื่อง Stern-Gerlach แกน Z เราพบว่ามีจุดปรากฏบนฉากรับเพียง 2 จุดเท่านั้น ไม่มีตำแหน่งอื่นเลย

**คณิตศาสตร์:** ตำแหน่งบนฉากคือปริมาณทางกายภาพที่เราวัดได้ (Observables) เมื่อเราดึงค่าคงที่ออกไป เราจะได้ตัวเลขที่เป็นผลลัพธ์ของการวัดเพียง 2 ค่าที่แน่นอน ให้เป็น $\textcolor{#FF80FF}{\lambda_\uparrow = +1} \in \textcolor{yellow}{\mathbb{R}}$ และ $\textcolor{#8080FF}{\lambda_\downarrow = -1} \in \textcolor{yellow}{\mathbb{R}}$ (ค่าเหล่านี้คือ Eigenvalues)

### 2. กำเนิดปริภูมิและเวกเตอร์สถานะ (State Space & Eigenvectors)

**ผลการทดลอง:** การที่ได้ผลลัพธ์แยกกัน 2 จุดชัดเจน (Mutually Exclusive) บังคับว่าระบบนี้มีสถานะที่แน่นอนเพียง 2 สถานะ

**คณิตศาสตร์:** ปริภูมิฮิลเบิร์ตมีมิติ $\dim \textcolor{yellow}{\mathcal{H}} = 2$

เราจะนิยามเวกเตอร์สถานะเชิงนามธรรม (Abstract state vectors) เพื่อมารองรับค่า $\textcolor{#FF80FF}{\lambda_\uparrow}$ และ $\textcolor{#8080FF}{\lambda_\downarrow}$:

- ให้ $\textcolor{#FF80FF}{|\uparrow_z\rangle}$ เป็นสถานะที่วัดแล้วได้ค่า $\textcolor{#FF80FF}{\lambda_\uparrow = +1}$

- ให้ $\textcolor{#8080FF}{| \downarrow_z \rangle}$ เป็นสถานะที่วัดแล้วได้ค่า $\textcolor{#8080FF}{\lambda_\downarrow = -1}$

สองสถานะนี้แยกแยะได้ 100% ไม่มีทางสับสนกัน แปลว่าความน่าจะเป็นที่จะพบอีกสถานะในอีกสถานะมีค่าเป็นศูนย์ ดังนั้นเวกเตอร์ต้องตั้งฉากกันสมบูรณ์: $\textcolor{#FF80FF}{\langle\uparrow_z}\textcolor{#FF4040}{|}\textcolor{#8080FF}{\downarrow_z\rangle} = \textcolor{#FF4040}{0}$

### 3. กำเนิดสมการค่าเฉพาะ (The Eigenvalue Equation)

**ผลการทดลอง (การวัดซ้ำ):** ถ้านำอิเล็กตรอนที่เพิ่งวัดผ่านเครื่องแรกได้ค่า "$\textcolor{#FF80FF}{+1}$" ไปยิงเข้าเครื่อง Stern-Gerlach แกน Z ตัวที่สอง มันจะพุ่งไปที่จุด "$\textcolor{#FF80FF}{+1}$" เสมอแบบ 100% (Reproducibility)

**คณิตศาสตร์:** เครื่องมือวัดในทางคณิตศาสตร์คือตัวดำเนินการ (Operator $\textcolor{cyan}{\hat{\sigma}_z}$) เพื่อให้สอดคล้องกับผลการวัดซ้ำ เมื่อ $\textcolor{cyan}{\hat{\sigma}_z}$ กระทำกับสถานะที่แน่นอน (เช่น $\textcolor{#FF80FF}{|\uparrow_z\rangle}$) มันจะต้อง **"ดึงตัวเลขผลการวัด (Eigenvalue) ออกมา โดยที่โครงสร้างของเวกเตอร์สถานะเดิมต้องไม่เปลี่ยนรูปไปเลย"** เพื่อให้การวัดครั้งต่อๆ ไปยังคงได้เวกเตอร์ตัวเดิมและค่าเดิม

นี่คือรากฐาน (Root cause) ว่าทำไมสมการจึงต้องอยู่ในรูปแบบนี้:

$$
\textcolor{cyan}{\hat{\sigma}_z} \textcolor{#FF80FF}{|\uparrow_z\rangle} = \textcolor{#FF80FF}{\lambda_\uparrow \vert{} \uparrow_z \rangle}
$$

$$
\textcolor{cyan}{\hat{\sigma}_z} \textcolor{#8080FF}{| \downarrow_z \rangle} = \textcolor{#8080FF}{\lambda_\downarrow \vert{} \downarrow_z \rangle}
$$

_(และเนื่องจาก \lambda ต้องเป็นค่าที่วัดได้จริงทางกายภาพ ($\textcolor{#FF80FF}{\lambda_\uparrow},\textcolor{#8080FF}{\lambda_\downarrow} \in \textcolor{yellow}{\mathbb{R}}$) จึงเป็นข้อบังคับตามมาว่าตัวดำเนินการนี้ต้องเป็น Hermitian operator $\textcolor{cyan}{\hat{\sigma}_z} = \textcolor{cyan}{\hat{\sigma}_z^\dagger}$ ในเวลาต่อมา)_

### 4. การประกอบเมทริกซ์และการเลือกฐาน (Operator Construction & Basis Choice)

จากเงื่อนไขในข้อ 3 เราสามารถประกอบตัวดำเนินการ $\textcolor{cyan}{\hat{\sigma}_z}$ ได้จากผลรวมของการฉายภาพ (Spectral Decomposition):

$$
\textcolor{cyan}{\hat{\sigma}_z} \equiv \textcolor{#FF80FF}{\lambda_\uparrow | \uparrow_z \rangle \langle \uparrow_z |} + \textcolor{#8080FF}{\lambda_\downarrow | \downarrow_z \rangle \langle \downarrow_z |}
$$

> [!note]- พิสูจน์ความสอดคล้องด้วยสมบัติความตั้งฉาก (Orthogonality)
> การประกอบตัวดำเนินการแบบ Spectral Decomposition นี้รับประกันสมการค่าเฉพาะ เนื่องจากเมื่อนำ $\textcolor{cyan}{\hat{\sigma}_z}$ ไปกระทำกับสถานะฐาน:
> **กระทำกับสถานะขึ้น:**
>
> $$
> \textcolor{cyan}{\hat{\sigma}_z} \textcolor{#FF80FF}{|\uparrow_z\rangle} =
> \textcolor{#FF80FF}{\lambda_\uparrow |\uparrow_z\rangle}
> \textcolor{#40FF40}{\underbrace{\textcolor{#FF80FF}{\langle\uparrow_z|\uparrow_z\rangle}}_{= 1}} +
> \textcolor{#8080FF}{\lambda_\downarrow |\downarrow_z\rangle}
> \textcolor{#FF4040}{\underbrace{\textcolor{#8080FF}{\langle\downarrow_z}|\textcolor{#FF80FF}{\uparrow_z\rangle}}_{= 0}} =
> \textcolor{#FF80FF}{\lambda_\uparrow |\uparrow_z\rangle}
> $$
>
> **กระทำกับสถานะลง:**
>
> $$
> \textcolor{cyan}{\hat{\sigma}_z} \textcolor{#8080FF}{|\downarrow_z\rangle} =
> \textcolor{#FF80FF}{\lambda_\uparrow |\uparrow_z\rangle}
> \textcolor{#FF4040}{\underbrace{\textcolor{#FF80FF}{\langle\uparrow_z}|\textcolor{#8080FF}{\downarrow_z\rangle}}_{= 0}} +
> \textcolor{#8080FF}{\lambda_\downarrow|\downarrow_z\rangle}
> \textcolor{#40FF40}{\underbrace{\textcolor{#8080FF}{\langle\downarrow_z|\downarrow_z\rangle}}_{= 1}} =
> \textcolor{#8080FF}{\lambda_\downarrow |\downarrow_z\rangle}
> $$
>
> ผลลัพธ์นี้เป็นจริงได้เพราะสถานะถูกเตรียมไว้อย่างสมบูรณ์แบบคือ $\textcolor{#FF80FF}{\langle\uparrow_z|\uparrow_z\rangle} = \textcolor{#8080FF}{\langle\downarrow_z|\downarrow_z\rangle} = \textcolor{#40FF40}{1}$ (Normalized) และแยกขาดจากกันเด็ดขาด $\textcolor{#8080FF}{\langle\downarrow_z}\textcolor{#FF4040}{|}\textcolor{#FF80FF}{\uparrow_z\rangle} = \textcolor{#FF80FF}{\langle\uparrow_z}\textcolor{#FF4040}{|}\textcolor{#8080FF}{\downarrow_z\rangle} = \textcolor{#FF4040}{0}$ (Orthogonal)

**การกำหนดฐาน (Arbitrary Choice):**

ถึงตรงนี้เราเพิ่งจะมากำหนดหน้าตาที่แท้จริงให้กับเวกเตอร์ $\textcolor{#FF80FF}{|\uparrow_z\rangle}$ และ $\textcolor{#8080FF}{| \downarrow_z \rangle}$ ในปริภูมิ $\textcolor{yellow}{\mathbb{C}^2}$ ซึ่งในทางฟิสิกส์เราจะ "สุ่มเลือก" (Arbitrary) เวกเตอร์คู่ไหนที่ตั้งฉากกันก็ได้ แต่เพื่อความสะดวกสูงสุด เราจะจับคู่มันเข้ากับฐานมาตรฐาน (Standard basis) ซึ่งสอดคล้องกับการวางตัวเป็นขั้วเหนือ-ใต้บนเรขาคณิตของ Bloch sphere และโครงสร้าง Spinor ของ Cartan:

$$
\textcolor{#FF80FF}{|\uparrow_z\rangle} = \textcolor{#FF80FF}{\begin{pmatrix} 1 \\ 0 \end{pmatrix}},
\quad \textcolor{#8080FF}{| \downarrow_z \rangle} = \textcolor{#8080FF}{\begin{pmatrix} 0 \\ 1 \end{pmatrix}}
$$

เมื่อแทนค่าคอลัมน์เวกเตอร์และโรว์เวกเตอร์ (Dual space) ลงในตัวดำเนินการ:

$$
\textcolor{cyan}{\hat{\sigma}_z} = \textcolor{#FF80FF}{(+1) \begin{pmatrix} 1 \\ 0 \end{pmatrix} \begin{pmatrix} 1 & 0 \end{pmatrix}} +
\textcolor{#8080FF}{(-1) \begin{pmatrix} 0 \\ 1 \end{pmatrix} \begin{pmatrix} 0 & 1 \end{pmatrix}}
$$

$$
\textcolor{cyan}{\hat{\sigma}_z} = \textcolor{#FF80FF}{\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}} + \textcolor{#8080FF}{\begin{pmatrix} 0 & 0 \\ 0 & -1 \end{pmatrix}} = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}
$$

### 5. ความไม่แน่นอนสัมบูรณ์ (Maximum Incompatibility)

**ผลการทดลอง:** หากเราเตรียมอิเล็กตรอนให้อยู่ในสถานะที่แน่นอนของแกน Z (เช่น $\textcolor{#FF80FF}{\vert{}\uparrow_z\rangle}$) แล้วนำไปยิงผ่านเครื่อง Stern-Gerlach ที่ตั้งในแนวแกน X หรือแกน Y ผลลัพธ์ที่ได้จะกลายเป็นการสุ่มสมบูรณ์ คือออก "ขึ้น" 50% และ "ลง" 50% เสมอ

**คณิตศาสตร์:** สถานะที่แน่นอนของแกน Z เมื่อถูกฉายภาพ (Project) ลงบนฐานการวัดของระนาบ XY ใดๆ จะต้องมีความน่าจะเป็นเท่ากับ $\frac{1}{2}$

กำหนดให้เวกเตอร์สถานะในระนาบ XY คือ $\textcolor{#FF80FF}{\vert{}\uparrow_{xy}\rangle} = \begin{pmatrix} \alpha \\ \beta \end{pmatrix} \in \textcolor{yellow}{\mathbb{C}^2}$

จากสมการความน่าจะเป็น $P = \vert{}\langle \text{basis} \vert{} \text{state} \rangle\vert{}^2$ เมื่อนำสถานะ $\textcolor{#FF80FF}{\vert{}\uparrow_z\rangle}$ ไปวัดในฐาน $\textcolor{#FF80FF}{\langle\uparrow_{xy}\vert{}}$ จะได้:

$$
P(\uparrow_{xy}) = \vert{}\textcolor{#FF80FF}{\langle\uparrow_{xy}} \textcolor{#FF4040}{\vert{}} \textcolor{#FF80FF}{\uparrow_z\rangle}\vert{}^2 = \left\vert{} \begin{pmatrix} \alpha^* & \beta^* \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} \right\vert{}^2 = \vert{}\alpha\vert{}^2 = \frac{1}{2}
$$

_(ทำนองเดียวกัน หากนำสถานะ $\textcolor{#8080FF}{\vert{}\downarrow_z\rangle}$ ไปวัด จะได้ $\vert{}\beta\vert{}^2 = \frac{1}{2}$)_

แปลว่าขนาด (Magnitude) ของ $\alpha$ และ $\beta$ ต้องเป็น $\frac{1}{\sqrt{2}}$ ส่วนเฟส (Phase) จะเป็นจำนวนเชิงซ้อนใดๆ ก็ได้ เมื่อเราดึง Global phase ทิ้งไป จะเหลือเพียงความต่างเฟสสัมพัทธ์ (Relative phase) $e^{i\phi}$:

$$
\textcolor{#FF80FF}{\vert{}\uparrow_{xy}\rangle} = \frac{1}{\sqrt{2}} \textcolor{#FF80FF}{\begin{pmatrix} 1 \\ e^{i\phi} \end{pmatrix}}, \quad \textcolor{#8080FF}{\vert{}\downarrow_{xy}\rangle} = \frac{1}{\sqrt{2}} \textcolor{#8080FF}{\begin{pmatrix} 1 \\ -e^{i\phi} \end{pmatrix}}
$$

_(เวกเตอร์ $\textcolor{#8080FF}{\vert{}\downarrow_{xy}\rangle}$ ได้มาจากข้อบังคับว่ามันต้องตั้งฉากกับสถานะขึ้น $\textcolor{#FF80FF}{\langle\uparrow_{xy}}\textcolor{#FF4040}{\vert{}}\textcolor{#8080FF}{\downarrow_{xy}\rangle} = \textcolor{#FF4040}{0}$)\_

### 6. การกำหนดแกน X และตัวดำเนินการ $\hat{\sigma}_x$ (Fixing the X-Axis)

**การกำหนดฐาน (Arbitrary Choice):**

ระนาบ XY ในปริภูมิฮิลเบิร์ตยังไม่มีจุดอ้างอิง เราจึงต้อง "สุ่มเลือก" จุดเริ่มต้น (Reference axis) โดยกำหนดให้แกน X คือแกนที่**ไม่มีความต่างเฟส** ($\phi_x = 0 \implies e^{i(0)} = 1$)

$$
\textcolor{#FF80FF}{\vert{}\uparrow_x\rangle} = \frac{1}{\sqrt{2}} \textcolor{#FF80FF}{\begin{pmatrix} 1 \\ 1 \end{pmatrix}}, \quad \textcolor{#8080FF}{\vert{}\downarrow_x\rangle} = \frac{1}{\sqrt{2}} \textcolor{#8080FF}{\begin{pmatrix} 1 \\ -1 \end{pmatrix}}
$$

**การประกอบเมทริกซ์:**

เราประกอบตัวดำเนินการ $\textcolor{cyan}{\hat{\sigma}_x}$ ด้วยวิธี Spectral Decomposition ชุดเดียวกับแกน Z โดยยึดค่าที่วัดได้จริง $\textcolor{#FF80FF}{\lambda_\uparrow = +1}$ และ $\textcolor{#8080FF}{\lambda_\downarrow = -1}$:

$$
\textcolor{cyan}{\hat{\sigma}_x} \equiv \textcolor{#FF80FF}{\lambda_\uparrow \vert{} \uparrow_x \rangle \langle \uparrow_x \vert{}} + \textcolor{#8080FF}{\lambda_\downarrow \vert{} \downarrow_x \rangle \langle \downarrow_x \vert{}}
$$

$$
\textcolor{cyan}{\hat{\sigma}_x} = \textcolor{#FF80FF}{(+1) \left[ \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix} \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \end{pmatrix} \right]} + \textcolor{#8080FF}{(-1) \left[ \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -1 \end{pmatrix} \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & -1 \end{pmatrix} \right]}
$$

$$
\textcolor{cyan}{\hat{\sigma}_x} = \textcolor{#FF80FF}{\frac{1}{2} \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}} - \textcolor{#8080FF}{\frac{1}{2} \begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}} = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}
$$

### 7. การกำหนดแกน Y และตัวดำเนินการ $\hat{\sigma}_y$ (Mutually Unbiased Bases)

**ผลการทดลอง:** หากเราเตรียมอิเล็กตรอนในสถานะที่แน่นอนของแกน X ($\textcolor{#FF80FF}{\vert{}\uparrow_x\rangle}$) แล้วนำไปวัดด้วยเครื่อง Stern-Gerlach แกน Y ผลลัพธ์ที่ได้ก็ยังคงสุ่มออกแบบ 50/50 เช่นกัน

**คณิตศาสตร์:** แกน X และ Y ต้องไม่เอนเอียงเข้าหากัน (Mutually Unbiased) นั่นคือ $P(\uparrow_y) = \vert{}\textcolor{#FF80FF}{\langle\uparrow_y} \textcolor{#FF4040}{\vert{}} \textcolor{#FF80FF}{\uparrow_x\rangle}\vert{}^2 = \frac{1}{2}$

เงื่อนไขนี้บีบบังคับให้ความต่างเฟส $\phi$ ของแกน Y ต้องตั้งฉากในระนาบเชิงซ้อน ($\phi_y = \frac{\pi}{2} \implies e^{i(\pi/2)} = i$)

$$
\textcolor{#FF80FF}{\vert{}\uparrow_y\rangle} = \frac{1}{\sqrt{2}} \textcolor{#FF80FF}{\begin{pmatrix} 1 \\ i \end{pmatrix}}, \quad \textcolor{#8080FF}{\vert{}\downarrow_y\rangle} = \frac{1}{\sqrt{2}} \textcolor{#8080FF}{\begin{pmatrix} 1 \\ -i \end{pmatrix}}
$$

**การประกอบเมทริกซ์:**

ใช้วิธี Spectral Decomposition เดิมเป๊ะๆ กับเวกเตอร์ของแกน Y:

$$
\textcolor{cyan}{\hat{\sigma}_y} \equiv \textcolor{#FF80FF}{\lambda_\uparrow \vert{} \uparrow_y \rangle \langle \uparrow_y \vert{}} + \textcolor{#8080FF}{\lambda_\downarrow \vert{} \downarrow_y \rangle \langle \downarrow_y \vert{}}
$$

_(ระวัง: ตอนทำ Dual space $\langle \text{Bra} \vert{}$ ต้องทำการ Conjugate เสมอ $i \to -i$)_

$$
\textcolor{cyan}{\hat{\sigma}_y} = \textcolor{#FF80FF}{(+1) \left[ \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ i \end{pmatrix} \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & -i \end{pmatrix} \right]} + \textcolor{#8080FF}{(-1) \left[ \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -i \end{pmatrix} \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & i \end{pmatrix} \right]}
$$

$$
\textcolor{cyan}{\hat{\sigma}_y} = \textcolor{#FF80FF}{\frac{1}{2} \begin{pmatrix} 1 & -i \\ i & 1 \end{pmatrix}} - \textcolor{#8080FF}{\frac{1}{2} \begin{pmatrix} 1 & i \\ -i & 1 \end{pmatrix}} = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}
$$
