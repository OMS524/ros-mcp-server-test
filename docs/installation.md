# Installation
## Linux (Ubuntu)

---

## 1. Install the MCP server
### 1.1 Install uv
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```
### 1.2 Test run ROS-MCP using uvx
```bash
# Test that the ROS-MCP server can be accessed in the venv
uvx ros-mcp --help
```

## 2. Install and configure a Language Model Client
### 2.1 Download
[claude-desktop-debian](https://github.com/aaddrick/claude-desktop-debian)
**Using APT Repository (Debian/Ubuntu - Recommended)**
```bash
# Add the GPG key
curl -fsSL https://aaddrick.github.io/claude-desktop-debian/KEY.gpg | sudo gpg --dearmor -o /usr/share/keyrings/claude-desktop.gpg

# Add the repository
echo "deb [signed-by=/usr/share/keyrings/claude-desktop.gpg arch=amd64,arm64] https://aaddrick.github.io/claude-desktop-debian stable main" | sudo tee /etc/apt/sources.list.d/claude-desktop.list

# Update and install
sudo apt update
sudo apt install claude-desktop
```











