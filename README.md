# Level Up Your Developer Onboarding with Dev Containers

This repository contains the slide presentation **Level Up Your Developer Onboarding with Dev Containers** (sponsored by Remake Labs) and serves as a demo of how Dev Containers simplify environment setup.

---

## Quick Start with Dev Containers

To simplify this demo, we will assume:

1. Container Runtime: Docker Desktop (we will still mention alternatives)
2. IDE: VSCode (But, the `devcontainer.json` file with work with other IDEs)

### If you have used containers before

1. **Clone this repository**

   ```bash
   git clone https://github.com/glenjarvis/talk-devcontainers
   cd talk-devcontainers
   ```

2. **Ensure you have the Microsoft Dev Containers extension installed in IDE (e.g., VSCode)**

   - Open VSCode, go to Extensions, and install: `ms-vscode-remote.remote-containers`

3. **Open the repo inside a Dev Container**

   - Open the Command Palette (menu: View -> Command Palette..., or press F1)
   - Then select `Dev Containers: Open Folder in Container`
   - Note #1: The container image may take a few minutes to download for the first time.
   - Note #2: You may be prompted to open automatically

4. **Verify Deno is available in the container**

   - Open the integrated terminal in VSCode (menu: View -> Terminal, or use the shortcut Ctrl+\` on Windows/Linux or Cmd+\` on macOS)

   ```bash
   $ deno --version
   deno 2.5.0 (stable, release, aarch64-unknown-linux-gnu)
   v8 14.0.365.4-rusty
   typescript 5.9.2
   ```

   Note: Even if your computer is a macOS or Windows computer, you will see `aarch64-unknown-linux-gnu`. This is running from inside the Dev Container
   which is Linux based.

5. **Ensure dependencies are installed**
   Deno will download and link npm dependencies the first time you run a task.
   To be explicit (similar to `npm install`), run:

   ```bash
   deno cache package.json
   ```

   Deno will install packages listed in `package.json` automatically.

   Glen's TODO: Eliminate this manual step by updating `devcontainer.json` to do this automatically:

   ```
   "postCreateCommand": "deno cache package.json && deno task dev --help"
   ```

6. **Start the slide presentation**
   ```bash
   deno task dev
   ```
   Then open the local URL (http://localhost:3030).

---

### If you have **never used containers before**

1. **Install Docker**

   - [Docker Desktop](https://www.docker.com/products/docker-desktop/) is free for educational purposes.
   - Alternatively, you may use [Rancher Desktop](https://rancherdesktop.io/) (open source, but more complex).

2. **Install the Microsoft Dev Containers extension**

   - In VSCode Extensions: `ms-vscode-remote.remote-containers`

3. **Clone this repository and open inside Dev Container**

   ```bash
   git clone https://github.com/glenjarvis/talk-devcontainers
   cd talk-devcontainers
   ```

   - Open in VSCode → Run: `Dev Containers: Open Folder in Container`

4. **Verify Deno inside the container**

   - Open the integrated terminal in VSCode (menu: View -> Terminal, or use the shortcut Ctrl+\` on Windows/Linux or Cmd+\` on macOS)

   ```bash
   $ deno --version
   deno 2.5.0 (stable, release, aarch64-unknown-linux-gnu)
   v8 14.0.365.4-rusty
   typescript 5.9.2
   ```

   Note: Even if your computer is a macOS or Windows computer, you will see `aarch64-unknown-linux-gnu`. This is running from inside the Dev Container
   which is Linux based.

5. **Ensure dependencies are installed**
   Deno will download and link npm dependencies the first time you run a task.
   To be explicit (similar to `npm install`), run:

   ```bash
   deno cache package.json
   ```

   Deno will install packages listed in `package.json` automatically.

   Glen's TODO: Eliminate this manual step by updating `devcontainer.json` to do this automatically:

   ```
   "postCreateCommand": "deno cache package.json && deno task dev --help"
   ```

6. **Start the slide presentation**
   ```bash
   deno task dev
   ```
   Then open http://localhost:3030.

---

## About This Repo

This repo is **primarily for slide content** (created with [Slidev](https://sli.dev/)), and **secondarily as a demo** to showcase how Dev Containers simplify onboarding.

By including `.devcontainer/devcontainer.json` and a `Dockerfile`, we ensure:

- No need to install Deno or Slidev locally
- Consistent environment across machines
- Quick onboarding for new developers

---

## Acknowledgements

- **Author:** Glen Jarvis (glen@glenjarvis.com)
- **Sponsor:** [Remake Labs](https://www.remakelabs.com/)
- Thanks to [Slidev](https://sli.dev/) and [Deno](https://deno.land/) communities.
