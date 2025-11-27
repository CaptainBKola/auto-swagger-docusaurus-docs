---

# **README.md**

# **Swagger to Docusaurus API Documentation Migration**

This project provides a complete pipeline for **migrating API documentation from Swagger/OpenAPI JSON into a fully structured Docusaurus documentation site**.

It includes:

* Conversion script for turning Swagger/OpenAPI JSON into Markdown
* Auto-generation of `/docs/api/` folder based on tags
* Auto-generation of `sidebars.api.js` for Docusaurus
* Support for versioning & future API updates
* Optional MCP integration to regenerate docs using an AI agent

This repository serves as a foundation for teams migrating from **Swagger UI** to a modern, flexible, documentation-driven platform.

---

## **Why This Migration?**

Swagger is great for API exploration, but not ideal for:

* Full developer documentation
* Content organization
* Versioning
* Custom UI/UX
* Integrating guides, tutorials, SDK docs
* Static hosting (GitHub Pages, Netlify, Vercel)

Docusaurus solves these problems by turning your API docs into:

* Markdown pages
* Versioned docs
* Searchable documentation
* A complete documentation website

This repo automates the migration so you never write endpoint docs manually again.

---

# **Project Structure**

```
root/
├── swagger.json                 # Your OpenAPI/Swagger spec (input)
│
├── scripts/
│   └── swagger-to-docusaurus.js # Converts Swagger → Docusaurus Markdown
│
├── docs-site/
│   ├── docs/
│   │   ├── intro.md
│   │   └── api/                 # Auto-generated API docs
│   │       ├── auth/
│   │       ├── users/
│   │       └── payments/
│   │
│   ├── sidebars.api.js         # Auto-generated sidebar
│   ├── docusaurus.config.js
│   └── package.json
│
├── package.json
└── README.md
```

---

# **Installation**

Clone the repository:

```bash
git clone https://github.com/<your-username>/swagger-docusaurus-docs.git
cd swagger-docusaurus-docs
```

Install dependencies:

```bash
npm install
```

Install Docusaurus dependencies:

```bash
cd docs-site
npm install
cd ..
```

---

# **Usage**

## **1. Place your Swagger/OpenAPI file**

Copy your JSON or YAML file into the root as:

```
swagger.json
```

Or:

```
openapi.json
```

---

## **2. Generate API Documentation**

From project root:

```bash
npm run gen:api
```

This will:

* Parse your Swagger spec
* Create Markdown files for each endpoint
* Group them by tags
* Create the Docusaurus sidebar file

Generated output lives in:

```
docs-site/docs/api/
```

---

## **3. Run the Documentation Website**

```bash
cd docs-site
npm run start
```

Your site is now available at:

```
http://localhost:3000
```

---

# **Optional: MCP Integration**

This repo supports an MCP tool that lets an AI agent regenerate documentation automatically.

Example MCP command:

```
/generate_api_docs
```

This triggers:

```
node scripts/swagger-to-docusaurus.js
```

This makes it possible to:

* Regenerate docs remotely
* Sync OpenAPI updates with Docusaurus
* Automate versioning and publishing

---

# **Tech Stack**

* **Docusaurus 3.x** - developer documentation site
* **Swagger / OpenAPI 3.x** - source of truth
* **Node.js** - migration + generation scripts
* **Prettier** - formatting
* **MCP (optional)** - automation

---

# **Folder Description**

| Folder/File                        | Purpose                              |
| ---------------------------------- | ------------------------------------ |
| `swagger.json`                     | Your Swagger/OpenAPI spec            |
| `scripts/swagger-to-docusaurus.js` | Converts Swagger → Markdown          |
| `docs-site/`                       | Docusaurus site folder               |
| `docs-site/docs/api/`              | Auto-generated API reference         |
| `sidebars.api.js`                  | Automatic API sidebar for Docusaurus |

---

# **Customization**

You can customise:

* Markdown templates
* Folder grouping logic
* Naming conventions (`get-users.md`, etc.)
* Sidebar structure
* Docusaurus theme & plugins

Just edit the generator script in `/scripts`.

---

# **Deployment**

Deploy your documentation to:

### **GitHub Pages**

```bash
npm run build
npm run deploy
```

### **Netlify / Vercel**

Just connect the `docs-site/` folder.

---

# **Contributions**

PRs and improvements are welcome.

If you want to extend:

* Redocly support
* YAML support
* Versioning automation
* SDK docs generation
* MCP agents

Feel free to open an issue.

---

# **License**

MIT License.

---

If you want, I can also create:

✔ A **GitHub Action** to automatically regenerate docs on every push
✔ A **Docusaurus landing page**
✔ A **sample Swagger file**
✔ A **folder for SDK docs (Node, Python, Go)**

Just tell me.
