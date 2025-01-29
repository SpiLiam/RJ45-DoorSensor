
    
    IN CONSTRUCTION
    
    
    🚀 R J 4 5 - D o o r S e n s o r 🚀  
   **A Smart Way to Monitor Your Rack Door!**  

---

# RJ45-DoorSensor 🛠️🔌  

🔹 **A passive magnetic door sensor** that uses a small **PCB adapter** to detect when a **server rack door** is **open** or **closed**.  
🔹 **No soldering required** – Just plug in the RJ45 cable & sensor wires! 🔌✨  
🔹 **Compatible with all Ethernet switches** that support **10/100 Mbps**. 📡  

📜 **License:** GPL-3.0  
📡 **Technology Used:** Ethernet, RJ45, Reed Switch, Custom PCB  
⚡ **Developed by:** Spiroy  

---

## 🎯 Features  

| Feature 🛠 | Description 📌 |
|-----------|--------------|
| 🚀 **Passive Monitoring** | Uses an Ethernet switch port to detect door status. |
| 🔌 **No Soldering Needed** | Plug in your RJ45 cable & sensor wires directly into the PCB. |
| 📡 **Compatible with Any 10/100 Mbps Switch** | Works with standard Ethernet switches. |
| 💰 **Ultra Low-Cost** | Uses a simple reed switch and a custom PCB. |
| 🛠 **Easy to Install** | Small PCB fits inside any rack cabinet. |

---

## 🔍 How It Works  

🎯 **Principle:** The PCB allows you to easily connect an RJ45 cable and a reed switch sensor to **interrupt the TX signal when the door is opened**.  

| **Door Status** | **Reed Switch** | **Ethernet Port** | **Monitoring Result** |
|--------------|--------------|----------------|------------------|
| ✅ **Closed** | Circuit **Complete** 🔗 | **UP** (Active) ✅ | Door is **closed**. |
| ❌ **Open** | Circuit **Broken** ❌ | **DOWN** (Inactive) ❌ | 🚨 Door is **open**! 🚨 |

📊 This status can be **monitored** via:  
✔️ **CLI on the switch** (via `show interfaces status`)  
✔️ **SNMP polling**  
✔️ **Syslog Alerts**  

---

## 🏗️ Hardware Requirements  

📌 **You’ll Need:**  

✔️ **Magnetic Reed Switch** (e.g., Window/Door Sensor)  
✔️ **RJ45 Ethernet Cable** (Standard, not modified!)  
✔️ **RJ45-DoorSensor PCB** (Custom adapter board 🛠️)  
✔️ **Compatible Ethernet Switch** (10BASE-T / 100BASE-TX)  

---

## 🛠️ Wiring & Assembly  

### 🧩 **Step 1: Connect the RJ45 Cable**  
🔹 Plug a **standard RJ45 cable** into the **RJ45-DoorSensor PCB**.  
🔹 The PCB internally routes the TX (Pin 2) through the reed switch.  

### 🔗 **Step 2: Attach the Reed Switch**  
🔹 **No soldering needed** – Connect the two wires from the reed switch to the PCB’s **screw terminals**.  
🔹 **When the door is closed**, the circuit remains **closed** ✅.  
🔹 **When the door is opened**, the circuit breaks ❌ → Port goes **DOWN**.  

### 📟 **Step 3: Configure the Switch**  

```bash
interface FastEthernet0/1
  no shutdown
  speed 10
  duplex half
  spanning-tree portfast
  switchport mode access
  no keepalive
```

🚀 **Done!** Now, whenever the door is opened, the port will go **DOWN**. You can set alerts via **SNMP** or **Syslog**! 📡🔔

---

## 📊 Usage  

✔️ **Step 1:** Plug in the RJ45 cable from the PCB into the switch.  
✔️ **Step 2:** Monitor the port via **CLI** / **SNMP** / **Syslog**.  
✔️ **Step 3:** Get alerts when the door is opened. 🚨  

**Example CLI Command:**
```bash
show interfaces status | include FastEthernet0/1
```
👀 **Expected Output:**  
- **UP** = Door **Closed** ✅  
- **DOWN** = 🚨 **ALERT! Door Opened!** ❌  

---

## 🔧 Custom Integrations  

You can extend **RJ45-DoorSensor** with:  
📡 **SNMP Traps** – Send alerts when the port goes DOWN!  
🖥️ **Network Monitoring (PRTG, Zabbix, Nagios, etc.)**  
🔔 **Syslog Alerts** – Log events when the door is opened.  

---

## 📜 License  

**RJ45-DoorSensor** is licensed under **GPL-3.0**.  
🔓 **Free to use, modify, and share!**  

---

## 🤝 Contributing  

We welcome contributions! 🎉  

🔹 **Fork** the repository  
🔹 **Create** a new branch (`git checkout -b feature/my-feature`)  
🔹 **Commit** your changes  
🔹 **Open a Pull Request**  

---

## 📩 Contact  

📢 **Project Owner:** Spiroy   
📡 **GitHub Issues:** Open a ticket if you have any questions!  

---

### 🎉 Thank you for using RJ45-DoorSensor! 🚀  
> **_"Making server room monitoring easy and effective."_**  

