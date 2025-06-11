# Flowchart Creator

Web Application: [Flowchart Creator by Minecraft AI](https://flowchart-creator.vercel.app/)

This is a simple web app for creating flowcharts in a Minecraft style UI. Have fun! 

![Screenshot 2025-06-06 at 21.08.46.png](https://s2.loli.net/2025/06/06/NGbkHC6Q1BIJspL.png)

Thanks to [Pollinations.AI](https://pollinations.ai/), we can generate a flowchart by just providing an idea!

## Minecraft AI

🧜 **Meet Max**, our AI assistant for the Minecraft AI community! Ask questions, get started with AIC profiles, or explore tutorials — Max@MinecraftAI ([Intl.](https://www.coze.com/s/ZmFp9aCtM/)/[CN](https://doubao.com/bot/8dV6HrwV)) is here to help.

🦾 This is created by Minecraft AI, welcome to join the our Discord server for more communications! 

<a href="https://discord.gg/RKjspnTBmb" target="_blank"><img src="https://s2.loli.net/2025/04/18/CEjdFuZYA4pKsQD.png" alt="Official Discord Server" width="180" height="32"></a>

## Projects by Minecraft AI

- [Minecraft AI](https://github.com/aeromechanic000/minecraft-ai) : This implementation is extended from the [MINDcraft](https://github.com/kolbytn/mindcraft) framework and is built on Node.js, utilizing the [Mineflayer](https://github.com/PrismarineJS/mineflayer) API. It provides fast deployment, real-time agent control, and flexible plugin support—making it especially suitable for live demos, interaction-heavy showcases, and rapid experimentation
- [Minecraft AI-Python](https://github.com/aeromechanic000/minecraft-ai-python) : This Python-based implementation reimagines the same agent logic in a more research-focused environment. It prioritizes system robustness, fine-grained control, and compatibility with
the Python scientific and AI tooling ecosystem. It is particularly well-suited for educational use, long-term
behavioral analysis, and the development of memory-rich agents.

## Tools by Minecraft AI 
- [Original Character for Minecraft AI](https://github.com/aeromechanic000/minecraft-ai-oc-creator) : A web app to create or edit the configuration of AI original character for Minecraft AI.
- [Minecraft 3D Skin Editor](https://github.com/aeromechanic000/minecraft-skin-editor-3d) : A simple web app for create and edit minecraft skin.
- [Flowchart Creator by Minecraft AI](https://github.com/aeromechanic000/flowchart-creator) : This is a simple web app for creating flowcharts in a Minecraft style UI.
- [Note Assistant by Minecraft AI](https://github.com/aeromechanic000/note-assistant) : A web app to prosses note with LLM.

## Reports by Minecraft AI
- [Minecraft AI Whitepapers](https://github.com/aeromechanic000/minecraft-ai-whitepaper) : The place where Minecraft AI whitepapers and technical reports are released.

## Prompt to Generate Flowchart of JSON Format

With the following prompt, you can generate flowcharts in JSON format with other LLM app, and import it. 

**Usage**
Replace `[INSERT YOUR WORKFLOW DESCRIPTION HERE]` with the idea.

```
Create a detailed flowchart based on the TASK DESCRIPTION.

Format your response as a valid JSON object with two arrays:

---

**"shapes"**: An array of shape objects, each with:

- "id": unique integer ID (start from 1)
- "type": one of "rectangle", "ellipse", "diamond", "parallelogram", "hexagon", "cylinder", or "circle"
- "x": x-coordinate (integer between 50–700)
- "y": y-coordinate (integer between 50–700)
- "width": 100–130 (recommended range)
- "height": 50–80 (recommended range)
- "text": text label for the shape
- "color": one of: "#f0f8ff", "#e1f5fe", "#f3e5f5", "#e8f5e8", "#fff3e0", "#ffebee", "#f5f5f5", "#fff9c4", "#ffffff"

---

**"arrows"**: An array of arrow objects, each with:

- "id": unique integer ID (continuing from shapes)
- "startId": ID of source shape
- "startPoint": one of "top", "right", "bottom", "left"
- "endId": ID of target shape
- "endPoint": one of "top", "right", "bottom", "left"
- "color": hex code (usually "#333333")

---

VISUAL DESIGN RULES

1. **Left-to-Right Alignment (Preferred)**
   - Organize flow from **left to right** to better use horizontal space.
   - Each "stage" in the process should form a vertical column, spaced horizontally.
   - Place sequential steps at the **same y-coordinate** but increasing x-coordinates.
   - Use vertical stacking only for subtasks or branches.

2. **Spacing Guidelines**
   - Maintain at least **150px horizontal spacing** between columns.
   - Leave at least **80px vertical spacing** between shapes in the same column.
   - No overlapping shapes.

3. **Logical Shape Usage**
   - Use:
     - `ellipse` for Start/End
     - `rectangle` for general steps
     - `diamond` for decisions/conditions

4. **Branching and Merging**
   - For decisions, branch left and right from a `diamond` using `"left"` and `"right"` connection points.
   - Merge back later using arrows from `"bottom"` or `"top"` into a common step.

5. **Arrow Clarity**
   - Use `"right"` for forward flow, `"left"` for backward flow, and vertical points for substeps.
   - Avoid arrow overlap or backtracking whenever possible.

6. **Label Clarity**
   - Keep text clear and concise (~30 characters max).
   - Break long process names into smaller blocks when needed.

---

TASK DESCRIPTION:
Provide a complete, valid JSON flowchart representing: "[INSERT YOUR WORKFLOW DESCRIPTION HERE]"

```
