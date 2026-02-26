# Installation
## Linux (Ubuntu)

---

## 1. Install the MCP server
### 1.1 Install uv
> ```bash
> curl -LsSf https://astral.sh/uv/install.sh | sh
> ```
### 1.2 Test run ROS-MCP using uvx
> ```bash
> # Test that the ROS-MCP server can be accessed in the venv
> uvx ros-mcp --help
> ```

## 2. Install and configure a Language Model Client
### 2.1 Download
[claude-desktop-debian](https://github.com/aaddrick/claude-desktop-debian)<br>
**Using APT Repository (Debian/Ubuntu - Recommended)**
> ```bash
> # Add the GPG key
> curl -fsSL https://aaddrick.github.io/claude-desktop-debian/KEY.gpg | sudo gpg --dearmor -o /usr/share/keyrings/claude-desktop.gpg
> 
> # Add the repository
> echo "deb [signed-by=/usr/share/keyrings/claude-desktop.gpg arch=amd64,arm64] https://aaddrick.github.io/claude-desktop-debian stable main" | sudo tee /etc/apt/sources.list.d/claude-desktop.list
> 
> # Update and install
> sudo apt update
> sudo apt install claude-desktop
> ```
### 2.2 Configure
`~/.config/Claude/claude_desktop_config.json` 해당 파일을 찾아서 편집하세요.<br>
해당 경로 및 파일이 없으면 생성하세요.<br>
JSON 파일의 `mcpServers` 섹션에 다음 내용을 추가하세요.<br>
> ```text
> {
>   "mcpServers": {
>     "ros-mcp-server": {
>       "command": "bash",
>       "args": [
>         "-lc", 
>         "uvx ros-mcp --transport=stdio"
>       ]
>     }
>   }
> }
> ```
### 2.3 Test the connection
터미널에서 다음 명령어를 실행하여 **Claude Desktop**을 실행하세요.
커넥터에 `ros-mcp-server`가 활성화 되어 있어야 합니다.
> ```bash
> claude-desktop
> ```
> <img width="1000" alt="image" src="https://github.com/user-attachments/assets/d51a6a6f-d9f1-4bcd-a1e5-7244e807fab3" />






