# 🌐 Cannet Network
### A Private, Decentralized Intranet Protocol
**GitHub Repository:** [smilos71/cannet](https://github.com/smilos71/cannet)

Cannet is a closed-loop network layer operating over the standard internet. It uses **WebSocket Tunnels** to host and access private `.can` domains without exposing users' public IP addresses or requiring complex network configurations.

---

## ⚠️ MANDATORY SECURITY & LEGAL DISCLAIMER

### 1. Security Risk
The `can.py` (Server) script is a **Minimalist Transparent Proxy**. It does not feature native filesystem sandboxing. 
- **NEVER** run the server script directly on your host OS. 
- **REQUIREMENT:** Use an isolated environment like **Docker** or **Pterodactyl**. 
- Failure to do so may expose your entire drive to **Directory Traversal attacks**.

### 2. Liability Limitation
The developers and operators of the Cannet Hub are **NOT RESPONSIBLE** for any content hosted by individual users on the network. 
- We do not host the data; we only provide the routing infrastructure (Relay).
- Users are solely responsible for the legality and nature of the content they provide through their `.can` nodes.
- By using Cannet, you agree that the developers are not liable for any data loss, legal consequences, or damages resulting from the use of this software.

---

## 🛠️ How to Connect (User/Visitor)

To browse the `.can` network, you need the **Cannet Browser Extension**. It works similarly to a VPN — you toggle it on when you want to enter the network.

1. **Download:** Get the `client.zip` from the [Releases](https://github.com/smilos71/cannet/releases) section.
2. **Installation:**
   - Use a Chromium-based browser (We strongly recommend **Ungoogled Chromium** or **Brave** for maximum privacy).
   - Go to `chrome://extensions/`.
   - Enable **"Developer mode"** (top right).
   - Click **"Load unpacked"** and select the folder extracted from `client.zip`.
3. **Usage:** - Open the extension popup and click **"Connect"**. 
   - While connected, you can access any `.can` address. 
   - Click **"Disconnect"** to return to normal browsing.

---

## 🏗️ How to Host (Server/Provider)

If you want to host your own website on the Cannet network:

1. **Requirements:** - **Python 3.8+** must be installed on your machine/container.
   - An active Cannet Token (issued by the administrator).
2. **Download:** Get the `server.zip` from the [Releases](https://github.com/smilos71/cannet/releases) section. It contains the `can.py` script.
3. **Configuration:** Edit `can.py` with your credentials:
   ```python
   # DO NOT CHANGE THE HUB_URL unless an official announcement is made 
   # on smilos71/cannet regarding a server IP change.
   HUB_URL = "ws://87.106.62.92:11697"
   
   MY_DOMAIN = "example.can"
   MY_TOKEN = "your_private_token"

 #  Privacy Note: The Hub is designed as a zero-log relay. Incoming traffic is processed in-memory and is never written to disk. However, as with any proxy-based network, users should avoid transmitting sensitive unencrypted credentials.
