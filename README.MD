<a href="https://github.com/wicorn29/chumbite-cfw">
  <img src="https://github.com/wicorn29/chumbite-cfw/blob/master/marketing/cbite.png?raw=true" alt="Chumbite Logo" width="50" height="50">
</a>

# Chumbite by Wicorn29

> Loosely based on Zurk’s offline firmware.  
> Modified and maintained by **Wicorn29** to run exclusively on the **Chumby Classic**, with a modernized backend and new endpoints.

---

## 📦 What Is This?

**Chumbite** is a USB-based custom firmware for the Chumby Classic that runs completely off a flash drive. It replaces the outdated and offline original Chumby services with fresh, self-hosted servers.  
It preserves the original Chumby look and feel while offering expanded features and future-proof functionality.

---

## 🌐 Server Endpoint

All traffic routes through:

```
https://chumbite.wicorn29.net
```

This is a backend-only endpoint. **No content is served** directly if you visit it via a browser.

---

## ⚙️ Features

- **Runs entirely from a USB stick** — no system modifications needed.
- **Original UI preserved** — feels just like stock Chumby.
- **Modern SSL support** through a required certificate patch.
- **DLNA/UPnP server built-in** (optional).
- **Offline-first** but connects to Chumbite server for enhanced functionality.
- **Reversible** — just remove the USB to return to stock.

---

## 🧰 Installation Instructions

> ⚠️ Only for the **Chumby Classic**.  
> 💾 Requires a **4GB or larger FAT32-formatted USB stick**.

---

### 🔐 Step 1: Install SSL Certificate Patch (REQUIRED)

> ⚠️ **NOTE: THIS WILL FACTORY RESET YOUR CHUMBY!**  
> All previous settings and data will be erased. Only proceed if you’re okay with this.

1. Format your USB stick as **FAT32**.
2. Download  `patchupdate.zip` from the here (scroll down)
3. Extract the contents of `patchupdate.zip` to the **root** of your USB drive.
 - *Note:* If extraction creates a folder (e.g., `patchupdate/`), open it and move its contents directly to the USB root.
5. Power off your Chumby.
6. **Enter Recovery Mode**:
   - Hold the touchscreen while powering on the device.
   - Wait for the **Special Options** screen.
7. Select:
   - `Install Updates` > `Install from USB Flash Drive`
8. Wait for installation to complete, then set up your chumby.
9. Turn chumby off.

---

### 📥 Step 2: Install Chumbite Firmware

1. Format the USB stick again (FAT32).
2. Download `chumbite.zip` from here.
3. Extract the contents of `chumbite.zip` to the **root** of the USB stick.
 - *Note:* If extraction creates a folder (e.g., `chumbite/`), open it and move its contents directly to the USB root.
5. Insert USB into Chumby Classic and power it on.
6. Chumbite will boot automatically.

---

### 🧼 Reverting to Stock Chumby

- To go back to your original Chumby setup:
  - Power off the device.
  - Remove the USB stick.
  - Power it on again — it will resume where it left off before Chumbite.
- If you want to load up chumbite again, repeat these steps but insert your chumbite usb stick.

---

## 🎶 Music & DLNA Notes

- **Pandora and official Chumby music services have been removed**.
- After booting Chumbite, open a browser and visit:

```
http://[chumby_ip_address]
```

Find your Chumby's IP in:
`Control Panel → Settings → Device Info → IP Address`

- You’ll see a **Chumbite Control Panel** with options:
  - Restore Chumby.com infrastructure (enables Pandora).
  - Use offline firmware’s music infrastructure.
  - Launch DLNA/UPnP configuration at `/dlna`.

📝 DLNA is **enabled by default**, and the file `dlna.on` controls this.  
To disable DLNA, simply **delete `dlna.on`** from the USB root.

> DLNA becomes available **~1 hour after boot**.  
Use any UPnP/DLNA server (e.g., MediaTomb) to stream music.

---

### 🎛️ Music and Podcast Customization

- Edit local radio stations:  
  Modify files in: `lighty/html/chumcast/list` and create `.xshow` files.

- After edits, run:

```bash
sync
```

- Customize podcasts via the **Podcast Editor** on the web control panel.
- Use the **Multi Channel Widget Editor** and **Weather Editor** to personalize the UI.
- Weather updates occur **hourly** — allow time for changes to reflect.

---

## 🌐 Chumote & Advanced Settings

- Navigate to your Chumby IP to access **Chumote!**, which lets you:
  - View the Chumby screen remotely.
  - Change parameters.
  - Start SSH access.

> For networks with security concerns, set a password with:
```bash
passwd root
```

---

## 📡 Network-less Mode

Want to run Chumbite completely offline?

- Delete `autoreboot.on` from `/mnt/usb` to enter **network-less mode**.
- This disables all network features until a reinstall is performed.

---

## 🔁 Final Setup Tips

- Always **sync** and **reboot** the Chumby after making configuration changes.
- Leave the USB plugged in to keep Chumbite running.
- Use a **dedicated** flash drive if you plan to use Chumbite long-term.

---

## 🙏 Credits

- Original concept and firmware structure: **Zurk**
- Heavy mods, hosting, and ongoing support: **Wicorn29**
- Server backend: [https://chumbite.wicorn29.net](https://chumbite.wicorn29.net)

---

Happy chumbing!
