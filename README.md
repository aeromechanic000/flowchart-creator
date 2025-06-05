# Flowchart Creator

Web Application: [Flowchart Creator by Minecraft AI](https://flowchart-creator.vercel.app/)

This is a simple web app for creating flowcharts in a Minecraft style UI. Have fun! 

Thanks to [Pollinations.AI](https://pollinations.ai/), we can generate a flowchart by just providing an idea!

## Minecraft AI
🦾 This is created by Minecraft AI, welcome to join the our Discord server for more communications! 

<a href="https://discord.gg/RKjspnTBmb" target="_blank"><img src="https://s2.loli.net/2025/04/18/CEjdFuZYA4pKsQD.png" alt="Official Discord Server" width="180" height="32"></a>

## Other Projects of Minecraft AI

- [Minecraft AI](https://github.com/aeromechanic000/minecraft-ai) : This implementation is extended from the [MINDcraft](https://github.com/kolbytn/mindcraft) framework and is built on Node.js, utilizing the [Mineflayer](https://github.com/PrismarineJS/mineflayer) API. It provides fast deployment, real-time agent control, and flexible plugin support—making it especially suitable for live demos, interaction-heavy showcases, and rapid experimentation
- [Minecraft AI-Python](https://github.com/aeromechanic000/minecraft-ai-python) : This Python-based implementation reimagines the same agent logic in a more research-focused environment. It prioritizes system robustness, fine-grained control, and compatibility with
the Python scientific and AI tooling ecosystem. It is particularly well-suited for educational use, long-term
behavioral analysis, and the development of memory-rich agents
- [Minecraft AI Whitepapers](https://github.com/aeromechanic000/minecraft-ai-whitepaper) : The place where Minecraft AI whitepapers and technical reports are released.

## Prompt to Generate Flowchart of JSON Format

With the following prompt, you can generate flowcharts in JSON format with other LLM app, and import it. 

**Usage**
Replace `${userInput}` with the idea.

```
Create a detailed flowchart based on the TASK DESCRIPTION.

Format your response as a valid JSON object with two arrays:
1. "shapes": An array of shape objects, each with:
   - "id": unique integer ID (start from 1)
   - "type": one of "rectangle", "ellipse", "diamond", "parallelogram", "hexagon", "cylinder", or "circle"
   - "x": x-coordinate (integer between 50-700)
   - "y": y-coordinate (integer between 50-400)
   - "width": width in pixels (usually 100-120)
   - "height": height in pixels (usually 50-70)
   - "text": text label for the shape
   - "color": color hex code (options: "#f0f8ff", "#e1f5fe", "#f3e5f5", "#e8f5e8", "#fff3e0", "#ffebee", "#f5f5f5", "#fff9c4", "#ffffff")

2. "arrows": An array of arrow objects, each with:
   - "id": unique integer ID (continuing from shapes)
   - "startId": ID of source shape
   - "startPoint": connection point ID ("top", "right", "bottom", "left")
   - "endId": ID of target shape
   - "endPoint": connection point ID ("top", "right", "bottom", "left")
   - "color": color hex code (usually "#333333")

Example:
{
  "shapes": [
    {"id": 1, "type": "ellipse", "x": 100, "y": 50, "width": 100, "height": 50, "text": "Start", "color": "#e8f5e8"},
    {"id": 2, "type": "rectangle", "x": 100, "y": 150, "width": 100, "height": 50, "text": "Process", "color": "#f0f8ff"},
    {"id": 3, "type": "diamond", "x": 90, "y": 250, "width": 120, "height": 60, "text": "Decision?", "color": "#fff9c4"}
  ],
  "arrows": [
    {"id": 4, "startId": 1, "startPoint": "bottom", "endId": 2, "endPoint": "top", "color": "#333333"},
    {"id": 5, "startId": 2, "startPoint": "bottom", "endId": 3, "endPoint": "top", "color": "#333333"}
  ]
}

IMPORTANT:
- Keep shapes well-spaced and organized logically
- Ensure arrows connect appropriate points (avoid crossing when possible)
- Make the flowchart accurately represent the process described
- Format your response ONLY as valid JSON that can be parsed with JSON.parse()
- Do not include any explanatory text outside the JSON object

TASK DESCRIPTION: 
Create a complete, valid JSON object for a flowchart representing: "${userInput}"
```
