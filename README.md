# PrivateRouter LuCi Theme for OpenWrt

**A modern, Material Design 3 inspired theme and simplified UI for OpenWrt routers** -- built for beginners, loved by OpenWRT nerds.

The PrivateRouter LuCi Theme transforms the standard OpenWrt LuCI interface into a clean, card-based experience that anyone can use. No terminal commands, no config files -- just a beautiful web UI for managing your router, your VPN connections, your Wi-Fi mesh network, and more.

The best part? It installs as a standard LuCI theme and **does not modify any OpenWrt core components**. Your existing LuCI setup stays completely intact, and you can switch back to the full advanced interface at any time with a single toggle.

![PrivateRouter LuCI Theme](https://raw.githubusercontent.com/torguardvpn/luci-theme-privaterouter/main/images/1.png)

---

## How It Works

The PrivateRouter Theme sits on top of LuCI as a standard OpenWrt theme package. It uses the same LuCI framework, the same UCI configuration system, and the same ubus RPC calls that power every OpenWrt router. Nothing is patched, replaced, or overwritten.

Three core packages work together to deliver the experience:

| Package | What It Does |
|---------|-------------|
| **luci-theme-oat** | The visual theme -- Material Design 3 styling, dark mode, the Simple/Advanced toggle, and all the icons and layout |
| **luci-mod-pr-dashboard** | A real-time dashboard with CPU/memory gauges, internet status, Wi-Fi info, VPN status, connected devices, and traffic stats |
| **luci-mod-simple** | The simplified interface pages -- Wi-Fi, Internet, VPN, Devices, Docker, System settings, and more |

Five additional packages provide optional VPN and mesh features. They are built from source in this repository and installable directly via the Software page in the simple UI:

| Package | What It Does |
|---------|-------------|
| **tgwireguard** | TorGuard WireGuard VPN LuCI UI |
| **tgwireguard2** | TorGuard WireGuard VPN second profile LuCI UI |
| **tgopenvpn** | TorGuard OpenVPN LuCI UI |
| **tgv2ray** | TorGuard V2Ray / sing-box LuCI UI |
| **luci-app-easymesh** | EasyMesh (Batman-adv) LuCI UI |

When you log in, you see the **Simple mode** by default: a clean sidebar with only the pages you need. Flip the **Simple / Advanced toggle** in the header bar and you get the full traditional LuCI menu with every option OpenWrt offers. Your preference is remembered across sessions.

```
Simple Mode                          Advanced Mode
+------------------+                 +------------------+
| Dashboard        |                 | Status           |
| Wi-Fi            |                 | System           |
| Internet         |                 | Network          |
| VPN              |                 | Firewall         |
| Devices          |                 | Services         |
| Docker           |                 | Docker           |
| System           |                 | NAS              |
| Logout           |                 | (all LuCI menus) |
+------------------+                 +------------------+
```

---

## Features at a Glance

![PrivateRouter LuCI Theme](https://raw.githubusercontent.com/torguardvpn/luci-theme-privaterouter/main/images/2.png)

### Modern Dashboard
Real-time system overview with animated CPU and memory gauges, WAN connection status with IPv4/IPv6 badges, wireless network details, download/upload traffic counters, storage usage bars, VPN tunnel status, and a connected devices list. Quick-access tiles link to the most common settings pages. Auto-refreshes every 5 seconds.

![PrivateRouter LuCI Theme](https://raw.githubusercontent.com/torguardvpn/luci-theme-privaterouter/main/images/9.png)

### Simple / Advanced Toggle
A toggle switch in the header bar lets you flip between the simplified UI and the full LuCI interface. In Simple mode, the sidebar shows only the clean, card-based pages. In Advanced mode, every standard LuCI menu appears. Switching to Simple mode from an advanced page automatically redirects you to the Dashboard.

### Dark Mode
Full dark mode support across every page, toggle it from the header bar. All cards, forms, gauges, and menus adapt seamlessly using CSS custom properties.

![PrivateRouter LuCI Theme](https://raw.githubusercontent.com/torguardvpn/luci-theme-privaterouter/main/images/5.png)

### TorGuard VPN Integration
Built-in pages for managing TorGuard VPN connections directly from the simple UI:

- **TorGuard WireGuard** -- Select a server from a global list (Americas, Europe, Asia Pacific, Middle East & Africa), enter your credentials, and connect. One-click start/stop with real-time tunnel status and traffic counters.
- **TorGuard OpenVPN** -- Full server list with protocol selection (UDP/TCP), port options, cipher configuration, and dedicated IP support.
- **TorGuard V2Ray** -- VPN and Proxy modes with VLESS, VMess, Trojan, and Shadowsocks support. Custom server import, SOCKS5/HTTP proxy ports, and sing-box powered.
- **Custom WireGuard** -- Bring your own WireGuard configuration from any provider.
- **VPN Status** -- Overview page showing all active tunnels with connection state, traffic stats, and quick links to each VPN configuration page.

![PrivateRouter LuCI Theme](https://raw.githubusercontent.com/torguardvpn/luci-theme-privaterouter/main/images/4.png)

### Easy Mesh Wi-Fi
Set up a mesh network across multiple OpenWrt routers without touching the command line. Choose between Server (Gateway) and Client roles, configure the mesh ID and Wi-Fi settings, enable 802.11k/v/r fast roaming (KVR), and let Easy Mesh handle the batman-adv networking. Includes a step-by-step setup guide modal built right into the page.

![PrivateRouter LuCI Theme](https://raw.githubusercontent.com/torguardvpn/luci-theme-privaterouter/main/images/10.png)

### Multi-Language Support
The simple UI is fully translated into **20 languages**, making it accessible to users worldwide:

| | | | |
|---|---|---|---|
| English | French | Japanese | Thai |
| Spanish | German | Korean | Turkish |
| Arabic (RTL) | Hindi | Polish | Ukrainian |
| Bengali | Indonesian | Portuguese | Vietnamese |
| Farsi (RTL) | Italian | Russian | Chinese |

Language selection is available from the header bar with country flag icons. Right-to-left (RTL) layout is fully supported for Arabic and Farsi.

![PrivateRouter LuCI Theme](https://raw.githubusercontent.com/torguardvpn/luci-theme-privaterouter/main/images/8.png)

### Additional Simple UI Pages

- **Wi-Fi Networks** -- View and edit SSIDs, passwords, encryption, and enable/disable radios
- **Guest Wi-Fi** -- Dedicated guest network management
- **Internet / WAN** -- Connection status with IP, gateway, DNS, uptime, and traffic
- **Firewall** -- Simplified firewall management
- **Adblock** -- Ad blocking configuration
- **IP Ban** -- IP ban list management (when banIP is installed)
- **IDS** -- Intrusion detection (when Snort is installed)
- **Connected Devices** -- DHCP client list with hostname, IP, MAC, and lease expiry
- **Storage** -- Disk and swap usage overview
- **Docker** -- Container management, an App Store catalog, and Docker settings (when Docker is installed)
- **Custom DNS** -- DNS server configuration
- **Admin Password** -- Change the router login password
- **Software** -- Install and remove packages including VPN and mesh bundles
- **Backup & Restore** -- Download and upload router configuration backups
- **System Update** -- Firmware update management
- **System Info** -- Hostname, memory, uptime, reboot

![PrivateRouter LuCI Theme](https://raw.githubusercontent.com/torguardvpn/luci-theme-privaterouter/main/images/7.png)

---

## Installation

### OpenWrt 25.x (apk-based)

OpenWrt 25.x replaced `opkg` with `apk`. Install the built `.apk` packages in this order:

**Step 1 -- Install the OAT Theme**

```bash
apk add --allow-untrusted luci-theme-oat_*.apk
```

**Step 2 -- Install the Dashboard Module**

```bash
apk add --allow-untrusted luci-mod-pr-dashboard_*.apk
```

**Step 3 -- Install the Simple UI Module**

```bash
apk add --allow-untrusted luci-mod-simple_*.apk
```

After installing all three, clear the LuCI cache and restart the web server:

```bash
rm -rf /tmp/luci-*
/etc/init.d/rpcd restart
/etc/init.d/uhttpd restart
```

### OpenWrt 24.10 and earlier (opkg-based)

Install all three `.ipk` packages **in this order** to satisfy dependencies:

**Step 1 -- Install the OAT Theme**

```bash
opkg install luci-theme-oat_*.ipk
```

**Step 2 -- Install the Dashboard Module**

```bash
opkg install luci-mod-pr-dashboard_*.ipk
```

**Step 3 -- Install the Simple UI Module**

```bash
opkg install luci-mod-simple_*.ipk
```

After installing all three, clear the LuCI cache and restart the web server:

```bash
rm -rf /tmp/luci-*
/etc/init.d/rpcd restart
/etc/init.d/uhttpd restart
```

Then open your router's web interface. The LuCi theme will be active and you will see the new simplified dashboard.

### Optional VPN and Mesh Packages

The TorGuard VPN and EasyMesh packages are included in the CI build artifacts alongside the core packages. To enable the built-in VPN and mesh pages, install them from the Software page in the simple UI, or manually.

**OpenWrt 25.x:**

```bash
apk add --allow-untrusted tgwireguard_*.apk tgwireguard2_*.apk
apk add --allow-untrusted tgopenvpn_*.apk
apk add --allow-untrusted tgv2ray_*.apk
apk add --allow-untrusted luci-app-easymesh_*.apk
```

**OpenWrt 24.10 and earlier:**

```bash
opkg install tgwireguard_*.ipk tgwireguard2_*.ipk
opkg install tgopenvpn_*.ipk
opkg install tgv2ray_*.ipk
opkg install luci-app-easymesh_*.ipk
```

---

## How the Simple / Advanced Toggle Works

The toggle is implemented entirely in the theme layer -- no LuCI core files are modified.

1. A **toggle switch** in the header bar stores your preference in the browser's `localStorage` as `oat-ui-mode` (either `"simple"` or `"advanced"`)
2. The `<html>` element receives a `data-ui-mode` attribute that CSS rules use to show or hide menu items
3. In **Simple mode**, only menu items with `admin/oat-*` and `admin/simple-*` paths are visible
4. In **Advanced mode**, those simplified items are hidden and the full LuCI menu tree appears
5. Switching to Simple mode from any advanced page automatically redirects to the Dashboard

This means every standard LuCI package, plugin, and configuration page continues to work exactly as before. The OAT theme simply controls which menu items are visible based on the selected mode.

---

## Project Structure

```
luci-theme-privaterouter/
├── luci-theme-oat/                  # Theme package
│   ├── htdocs/luci-static/oat/      # CSS, JS, fonts, icons, logo
│   ├── ucode/template/themes/oat/   # Header, footer, login templates
│   └── root/etc/uci-defaults/       # Auto-activate theme on install
│
├── luci-mod-pr-dashboard/           # Dashboard module
│   ├── htdocs/.../view/dashboard/   # Dashboard JS, CSS, icons
│   └── root/usr/libexec/            # VPN status detection script
│
├── luci-mod-simple/                 # Simplified UI module
│   ├── htdocs/.../view/simple/      # 25+ page JS files, CSS
│   │   ├── i18n/                    # 20 language translation files
│   │   ├── flags/                   # Country flag SVGs
│   │   └── appstore/                # Docker app catalog
│   └── root/usr/share/              # Menu definitions, ACL permissions
│
├── tgwireguard/                     # TorGuard WireGuard LuCI UI
├── tgwireguard2/                    # TorGuard WireGuard profile 2 LuCI UI
├── tgopenvpn/                       # TorGuard OpenVPN LuCI UI
├── tgv2ray/                         # TorGuard V2Ray LuCI UI
└── luci-app-easymesh/               # EasyMesh (Batman-adv) LuCI UI
```

---

## Building from Source

Packages are built automatically via GitHub Actions using the [openwrt/gh-action-sdk](https://github.com/openwrt/gh-action-sdk). Trigger a build manually from the Actions tab, or push to `main`. Artifacts (`.apk` for OpenWrt 25.x) are attached to each workflow run.

To build locally using the OpenWrt SDK:

```bash
# Clone into a directory the SDK can find as a feed
git clone https://github.com/ok11/luci-theme-privaterouter

# Add as a feed in feeds.conf
echo "src-link action /path/to/luci-theme-privaterouter" >> feeds.conf

# Update and install
./scripts/feeds update action
./scripts/feeds install luci-theme-oat luci-mod-pr-dashboard luci-mod-simple \
    tgwireguard tgwireguard2 tgopenvpn tgv2ray luci-app-easymesh

# Build all packages
make package/luci-theme-oat/compile
make package/luci-mod-pr-dashboard/compile
make package/luci-mod-simple/compile
make package/tgwireguard/compile
make package/tgwireguard2/compile
make package/tgopenvpn/compile
make package/tgv2ray/compile
make package/luci-app-easymesh/compile
```

The resulting `.apk` (or `.ipk` on older SDKs) files will be in `bin/packages/`.

### Updating the TorGuard and EasyMesh packages

The `tgwireguard`, `tgwireguard2`, `tgopenvpn`, `tgv2ray`, and `luci-app-easymesh` package source files are committed directly to this repo. They were originally extracted from TorGuard-supplied `.ipk` files. Since these are closed-source LuCI UI wrappers, there is no upstream source URL to track automatically -- they must be updated manually when TorGuard ships new versions.

To update a package from a new `.ipk`:

```bash
# Extract the new ipk
mkdir /tmp/pkg && cd /tmp/pkg
cp /path/to/tgwireguard_NEW_VERSION_all.ipk pkg.ipk
tar xzf pkg.ipk          # extracts control.tar.gz and data.tar.gz
tar xzf data.tar.gz      # extracts the installed file tree

# Copy updated files into the repo, replacing the old ones
cp -r . /path/to/luci-theme-privaterouter/tgwireguard/root/

# Update PKG_VERSION in the Makefile, commit, and push
```

---

## Compatibility

| OpenWrt version | Package format | Status |
|----------------|---------------|--------|
| 25.x (SNAPSHOT) | `.apk` | Supported |
| 24.10 | `.ipk` | Supported |
| 23.05 | `.ipk` | Should work |

- Works with any OpenWrt device that supports LuCI
- Responsive layout adapts to desktop, tablet, and mobile screens
- Self-contained -- no external CDNs, fonts, or JavaScript libraries required
- All assets (CSS, JS, SVG icons, translations) are bundled in the packages

---

## Credits

- [OpenWrt LuCI](https://github.com/openwrt/luci) -- the web interface framework this theme extends
- [Material Design 3](https://m3.material.io/) -- design language inspiration
- [MDUI](https://www.mdui.org/) -- Material Design UI component reference
- [TorGuard](https://torguard.net/) -- VPN service integration
- [PrivateRouter](https://www.privaterouter.com/) -- project sponsor and maintainer

## License

MIT
