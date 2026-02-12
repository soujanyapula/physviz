**⚡ PHYSVIZ — AI-Powered Physics Problem Visualizer**

**📌 Project Title:-**

**PhysViz** is an AI-powered, browser-based physics problem visualizer. It converts natural language physics word problems into real-time, interactive simulations — no installation, no server, just open and run.

**📖 Description:-**

PhysViz bridges the gap between textual physics problems and conceptual understanding. A student or educator simply types a physics word problem in plain English — for example, *"A ball is thrown at 20 m/s at an angle of 45 degrees"* — and the app does the rest.

Under the hood, PhysViz uses the **Anthropic Claude API** to parse the problem and extract key parameters like mass, velocity, angle, and gravity. It then identifies the correct simulation type — projectile motion, pendulum, spring oscillation, inclined plane, free fall, elastic collision, or linear motion — and instantly renders a **live, animated Canvas-based simulation** with real-time physics calculations running frame by frame.

Alongside the animation, the app displays the **governing equations** and live-computed values such as displacement, velocity, acceleration, momentum, and energy. Users can also tweak any parameter on the fly using sliders or the **inline Live Parameter Editor**, and the simulation restarts instantly without needing to re-type the problem.

> **The entire app is a single `physviz.html` file** — completely client-side, with zero build steps and zero npm packages.

**🛠️ Tech Stack:-**

PhysViz is built entirely with **Vanilla JavaScript (ES6+), HTML5, and CSS3** — no frameworks, no bundlers. The physics simulations are drawn using the **HTML5 Canvas 2D API**, which handles all animation rendering directly in the browser.

For AI-powered problem parsing, the app makes a direct `fetch` call to the **Anthropic Claude API** (model: `claude-sonnet-4-5-20250929`). Typography is handled by **Google Fonts**, using Orbitron for headings and IBM Plex Mono for the monospace body text. The layout uses CSS Grid and Flexbox with custom CSS properties for theming, and all animations are pure CSS keyframes — no animation libraries needed.

> **Runtime:** Browser-only. No Node.js, no bundler, no build step required.

 **🚀 How to Run the Project:-**

**The simplest way** is to just double-click `physviz.html` and open it in any modern browser. You can also drag and drop the file directly into a browser window.

**The recommended way** is to serve it via a local HTTP server, because some browsers block `fetch` API calls made from `file://` URLs. If you have Python installed, run `python3 -m http.server 8080` in the project folder and open `http://localhost:8080/physviz.html` in your browser. If you use Node.js, run `npx serve .` and follow the URL it prints. VS Code users can install the **Live Server** extension and right-click `physviz.html` → *Open with Live Server*.

**📦 Dependencies:-**

PhysViz has **zero npm or pip dependencies**. There is no `package.json` and no `node_modules` folder. The only external resources the app loads at runtime are the **Anthropic Claude API** (called via `fetch` for AI parsing) and **Google Fonts** (loaded via a CDN `<link>` tag for typography). Fonts are purely cosmetic — the app still works if they fail to load. The Claude API call, however, is required for the AI parsing feature to function.

**⚠️ Important Instructions:-**

**🌐 Internet Connection:-**

An active internet connection is required to load Google Fonts and — more importantly — to call the Anthropic Claude API. The app will not be able to parse physics problems in offline mode.

**🌍 CORS and Browser Restrictions:-**

If you open the file directly from `file://` and the browser blocks the API call due to CORS policy, switch to a local HTTP server as described in the *How to Run* section above. Chrome and Edge are the most likely to enforce this restriction on local files.

**🖥️ Browser Compatibility:-**

The app works fully on **Chrome 90+, Firefox 88+, Edge 90+, and Safari 14+**. Internet Explorer is not supported.

**🎮 Supported Simulation Types:-**
**PhysViz can detect and animate 8 types of physics scenarios:**

1)Vertical Projectile Motion

2)Angled Projectile Motion

3)Linear Motion

4)Simple Pendulum

5)Inclined Plane

6)Spring-Mass Oscillation

7)Free Fall

8)Elastic Collision

**Each simulation shows:**

1)Live velocity vectors

2)Real-time values

3)Governing equations

PhysViz can detect and animate **8 types of physics scenarios** from plain English input. These are: **Vertical Projectile Motion** (e.g. a ball thrown straight up), **Angled Projectile Motion** (trajectory with X and Y components), **Linear Motion** (objects with constant acceleration), **Simple Pendulum** (oscillation with period and angle), **Inclined Plane** (block sliding down a slope), **Spring-Mass Oscillation** (Hooke's Law animation), **Free Fall** (object dropped from height), and **Elastic Collision** (two-body momentum and energy conservation). Each simulation shows live velocity vectors, real-time values, and the relevant governing equations.

**🎬 Demo Videos of MVP:-**

- Full Walkthrough:- https://drive.google.com/file/d/12irau5C22SXBzZBSI-Ty_w-IirvPm2Km/view?usp=sharing

**📁 Project Structure:-**

The entire application is a **single self-contained file**. There are no folders, no assets directory, and no config files.

physviz/
├── physviz.html     ← The entire application lives here
└── README.md        ← This file

**⚠️ Known Issues / Limitations:-**
Since PhysViz is an MVP built during a hackathon, there are a few known limitations to be aware of. The API key is embedded client-side in the HTML file, which means it is visible to anyone who views the page source — this is acceptable for demos but must be fixed before any public deployment. The AI parser works best with clean, well-structured problem statements; ambiguous or very complex multi-body problems may not be parsed correctly or may fall back to a default simulation. The app currently supports only 8 simulation types, so problems outside these categories (e.g. rotational dynamics, thermodynamics, or wave optics) will not produce a meaningful visualization. Additionally, since all rendering happens on a single HTML Canvas, very fast simulations may appear choppy on low-end devices or older browsers. There is also no offline mode — without an internet connection, the AI parsing feature does not work at all.

**🔭 Future Scope:-**
There are several directions in which PhysViz could be expanded beyond the current MVP. The most impactful next step would be adding a backend proxy server to securely handle API keys instead of exposing them in the browser. On the simulation side, support could be extended to cover rotational motion, wave physics, electric fields, and fluid dynamics, making the tool useful for a much wider range of physics topics. A 3D rendering mode using WebGL or Three.js would allow more realistic visualizations, especially for projectile and orbital mechanics problems. The Live Parameter Editor could be enhanced with drag-and-drop interaction directly on the canvas — for example, dragging a projectile's launch angle visually. Longer term, PhysViz could evolve into a full classroom tool with problem-saving, shareable simulation links, and an embedded quiz mode that asks students to predict outcomes before running the simulation.

**👥 Team:-**

**TEAM NULLVEX** — VNR VJIET AI-Week Vibe Coding Hackathon 2026
This project was built by three members. **Soujanya Pula** led the team as Team Lead, with **Shahaana Shaik** and **Jahnavi Vattepu** as core team members.

**📄 License:-**

Built for hackathon demonstration purposes. All rights reserved by Team Nullvex.
