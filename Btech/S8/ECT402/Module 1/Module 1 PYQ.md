
# Module 1 PYQ

> See: [[PYQ Index]] | [[most_asked_questions]]

### **List the different types of Wireless LAN topologies** 

Based on the text, wireless networks are set up in two primary modes (topologies):

- **Infrastructure Network Mode:** Communication takes place **indirectly through a central access point**, **which acts as a bridge and handles medium access control**.
- **Ad-Hoc Network (Peer-to-Peer) Mode:** A decentralized network that does not rely on pre-existing infrastructure. Nodes communicate directly with each other and participate in routing by forwarding data for other nodes dynamically.
> [!info]- What is Ad-Hoc Mode?
> **Simple explanation:** No central router needed. Devices talk directly to each other.
> - **Decentralized:** No access point/router control
> - **No infrastructure:** Works without any pre-existing network
> - **Dynamic routing:** Each device can relay messages for others
> **Example:** You and friends in a remote area can connect phones directly without WiFi. If your phone can't reach someone far away, a friend in between can pass your message along.

### **Describe the different types of handoff schemes used in cellular networks?**

Handoffs are broadly classified into two categories:

- **Hard Handoff:** This is a **"break-before-make"** process where the connection to the old base station (BS) is broken before a connection to the new BS is made. It typically occurs between disjointed radio systems or different frequency assignments.
- **Soft Handoff:** This is a **"make-before-break"** process where the mobile establishes a connection to the new BS before breaking the connection to the old BS.

**Part B**

### **Explain the concept of soft handoff and hard handoff in cellular networks. How do they differ and what are their advantages and disadvantages?**

- **Hard Handoff:** Operates on a **"break-before-make"** principle. The connection to the existing base station is terminated before connecting to the new one. It is used when handing off between different frequency assignments or disjointed radio systems (like intracellular and intercellular handoffs). **Disadvantage:** If the signal threshold margin (Δ) is too small, there might be insufficient time to complete the handoff, leading to a dropped or lost call.
- **Soft Handoff:** Operates on a **"make-before-break"** principle. The mobile unit connects to the new base station before disconnecting from the old one, ensuring seamless connectivity. **Advantage:** Soft handoff allows multiple base-stations to simultaneously decode the mobile's data, providing an extra level of diversity to the users and reducing the chance of dropped calls.





### **1. Channel Assignment Strategies**

The primary goal of channel assignment strategies is to optimize frequency reuse and minimize interference to increase overall channel capacity. They dictate how calls are managed when a user moves between cells:

- **Fixed Channel Allocation (FCA):** Each cell is assigned a specific, predetermined set of voice channels. If all channels in a cell are busy, new calls are blocked. FCA may use a "borrowing approach" where a cell can borrow channels from a neighboring cell (supervised by the Mobile Switching Centre, or MSC) as long as it doesn't cause interference. FCA is highly efficient under uniform traffic but wastes resources when traffic is non-uniform.
- **Dynamic Channel Allocation (DCA):** Channels are pooled rather than permanently assigned to specific cells. When a cell needs a channel, it requests one from the MSC, which assigns it based on real-time data like traffic distribution, likelihood of future blocking, and the required frequency reuse distance to avoid interference. DCA increases channel utilization and decreases blocked calls but requires a heavy computational load on the MSC.
- **Hybrid Channel Allocation:** This is a mix of both fixed and dynamic allocation methods.

### **2. Handoff Strategies**

**Handoff** is the process of transferring an active call from one base station (BS) to another as the mobile unit moves, without disconnecting the call.

- **The Handoff Process:** When a mobile's signal at the current BS weakens while simultaneously improving at a neighboring BS, the MSC initiates a handoff. To do this properly, designers set a threshold margin: Δ=Pr_handoff​−Pr_minimum_usable​. If Δ is too large, the MSC gets burdened with unnecessary handoffs. If Δ is too small, there isn't enough time to complete the handoff, and the call drops due to weak signals.
- **Types of Handoff:**
    - **Hard Handoff:** A "break-before-make" scenario where the connection to the old BS is broken before connecting to the new one (common when changing frequencies or moving between disjointed systems).
    - **Soft Handoff (SHO):** A "make-before-break" scenario where the mobile connects to more than one BS simultaneously until the transition is fully complete.
- **Deciding Factors:** Handoff decisions rely on the transmitted signal strength, vehicle speed (steep signal drops require faster handoffs), and the dwell time (how long a call is maintained within a single cell).

### **3. Interference and System Capacity**

**Interference** is a major bottleneck in cellular systems, causing cross-talk on voice channels and missed or dropped calls on control channels. It is generally harder to control than capacity issues.

- **System Capacity:** Overall capacity is capped by three bottlenecks: radio capacity, control link capacity, or switch capacity. Improving radio capacity alone is useless if the switch capacity isn't large enough to handle the traffic.
- **Co-Channel Interference:** Occurs between cells using the exact same frequency channels. It cannot be fixed by increasing transmitter power (which would just cause more interference). Instead, it is minimized by physically separating co-channel cells by a "frequency reuse distance" (D). The ratio q=D/R (where R is the cell radius) relates directly to the cluster size N (q=3N![](data:image/svg+xml;utf8,<svg%20xmlns="http://www.w3.org/2000/svg"%20width="400em"%20height="1.08em"%20viewBox="0%200%20400000%201080"%20preserveAspectRatio="xMinYMin%20slice"><path%20d="M95,702%0Ac-2.7,0,-7.17,-2.7,-13.5,-8c-5.8,-5.3,-9.5,-10,-9.5,-14%0Ac0,-2,0.3,-3.3,1,-4c1.3,-2.7,23.83,-20.7,67.5,-54%0Ac44.2,-33.3,65.8,-50.3,66.5,-51c1.3,-1.3,3,-2,5,-2c4.7,0,8.7,3.3,12,10%0As173,378,173,378c0.7,0,35.3,-71,104,-213c68.7,-142,137.5,-285,206.5,-429%0Ac69,-144,104.5,-217.7,106.5,-221%0Al0%20-0%0Ac5.3,-9.3,12,-14,20,-14%0AH400000v40H845.2724%0As-225.272,467,-225.272,467s-235,486,-235,486c-2.7,4.7,-9,7,-19,7%0Ac-6,0,-10,-1,-12,-3s-194,-422,-194,-422s-65,47,-65,47z%0AM834%2080h400000v40h-400000z"></path></svg>)​).
- **Adjacent Channel Interference:** Occurs when frequencies of adjacent channels leak into the desired channel, often causing the "near-far problem" where a nearby transmitter captures the receiver. It is mitigated by careful filtering, maximizing frequency separation between adjacent cells, and using constant power control to ensure mobiles transmit at the lowest possible power.

### **4. Trunking and Grade of Service**

- **Trunking:** This concept allows a large number of users to share a much smaller number of mobile channels by assigning channels strictly on a demand basis. When a call terminates, the channel is immediately returned to the available pool for the next user. Traffic intensity in this system is measured in **Erlangs**.
- **Grade of Service (GOS):** GOS is the benchmark of a trunked system's performance, representing the probability that a call will be blocked or delayed beyond an acceptable time limit during the busiest hour of the day (statistically around 4 PM to 6 PM). For instance, a system designed for a 2% GOS implies that 2 out of every 100 calls attempted during the busiest hour will be blocked.

### **5. Improving Coverage and Capacity**

When demand exhausts the available channels in a cell, techniques are deployed to serve more channels per unit of coverage area:

- **Cell Splitting:** A congested cell is subdivided into smaller cells (microcells), each getting its own new base station. To maintain the frequency reuse plan and limit interference, the antenna heights and transmitter powers must be drastically reduced. For example, halving the radius of a cell requires dropping the transmit power by 12 dB.
- **Cell Sectoring:** Instead of building new base stations, an existing cell is split into angular sectors (like 120° or 60° slices). An omnidirectional antenna is replaced by several directional antennas, which radiate only within their sector. Because the antennas only broadcast in specific directions, co-channel interference is vastly reduced, allowing the Signal-to-Interference Ratio (SIR) to increase.
- **Microcell Zone Concept:** Similar to sectoring, but better. Multiple zone sites (Tx/Rx antennas) are placed at the edges of a cell and connected back to a single, central base station using coaxial cables or microwave links. As a mobile travels through the cell, it is automatically served by the zone with the strongest signal using the same channel equipment at the base station. This eliminates the need for handoffs between zones and actively reduces interference since the channel is only transmitting in the exact zone the mobile currently occupies.

### **What is the difference between microdiversity and macrodiversity?**

### **How does the Alamouti scheme provide transmit diversity?**

### **Explain the near-far problem in adjacent channel interference.**

can you look at qp 1.pdf and qp 2.pdf and answer all questions from module 1

**From Question Paper 1 (0400ECT402012402)**

**Part A**


### **Q11 b) If a cellular system supports 150 simultaneous calls per cell and each call requires 24 kbps, determine the bandwidth needed for a 4-cell cluster.**

- **Given:**
    - Simultaneous calls per cell = 150
    - Bandwidth per call = 24 kbps
    - Cluster size (N) = 4 cells
- **Calculation:**
    - Total number of simultaneous calls per cluster = Calls per cell×Number of cells in cluster=150×4=600 calls.
    - Total bandwidth needed for the cluster = Total calls×Bandwidth per call=600×24 kbps=14,400 kbps (or **14.4 Mbps**).

### **Q12 a) Compare and contrast the important performance features of 4G and 5G wireless communication systems.** According to the comparison table:

- **Data Bandwidth:** 4G supports 2 Mbps to 1 Gbps, while 5G targets at least 1 GB/s to 10 GB/s to support ultra-high-definition video, virtual reality, and mobile cloud services.
- **Core Network:** 4G utilizes an All IP network. 5G uses a Flatter IP Network and 5G Network Interfacing (5G-NI).
- **Service Features:** 4G features dynamic information access, wearable devices, and HD streaming. 5G expands on this to support all upcoming global technologies and seamless global roaming.
- **Switching:** 4G utilizes Packet switching, whereas 5G utilizes All Packet switching.

### **Important Features of 5G System:**

- **Ultra-fast speeds:** Mobile internet data rates up to 10 Gbps.
- **Low latency:** Response times in milliseconds, which is crucial for mission-critical applications.
- **Advanced technologies:** Utilizes massive MIMO, small cells, and beamforming to improve efficiency.
- **Flexible architecture:** Uses software-defined, cloud-based infrastructure for agile, power-efficient maintenance.
- **Enhanced security:** Offers a more reliable and highly secure network.


| Feature | Description |
|---------|-------------|
| **Data Rate** | 1-10 Gbps (10x faster than 4G) |
| **Latency** | <1 ms (vs 50ms in 4G) |
| **Capacity** | 100x more devices per sq km |
| **Frequency** | mmWave (24-100 GHz) + sub-6 GHz |
| **Spectrum** | Licensed + unlicensed + shared |
| **Massive MIMO** | 64-256 antenna elements |
| **Network Slicing** | Multiple virtual networks on one physical infrastructure |
| **Beamforming** | Directional signal focus for better coverage |
| **D2D Communication** | Direct device-to-device without base station |
| **Ultra-Reliable Low-Latency (URLLC)** | Mission-critical applications |
| **IoT Support** | Massive machine-type communications |
| **Energy Efficiency** | Better power management |

### **Q12 b) Explain the techniques that can be used to improve the capacity of a cellular system?** To increase capacity when channels become insufficient, the following cellular design techniques are used:

- **Cell Splitting:** A congested cell is subdivided into smaller microcells, each with its own base station, reduced antenna height, and reduced transmitter power. This increases capacity by increasing the number of times channels are reused over the area.
- **Cell Sectoring:** A single cell is divided into angular sectors (e.g., 120∘ or 60∘) using directional antennas instead of an omnidirectional one. This increases capacity by reducing co-channel interference, which improves the Signal-to-Interference Ratio (SIR) without requiring new base stations.
- **Microcell Zone Concept:** Multiple zone sites (antennas) are placed at the edges of a cell and connected back to a single central base station. A mobile is served by the zone with the strongest signal using the same channel. This increases capacity without degrading trunking efficiency and reduces interference because the channel is only active in the specific zone the mobile occupies.

--------------------------------------------------------------------------------

**From Question Paper 2 (0400ECT402052301)**

**Part A**

### **Compare and contrast the analog and digital cellular systems** 

Based on the comparison between 1G (analog) and 2G (digital) systems:

- **Technology:** Analog systems (1G) rely on analog voice technology, whereas digital systems (2G) rely on digital switching and transmission technology.
- **Bandwidth/Data:** Analog systems offer low data speeds (around 1.9 kbps), whereas digital systems support higher capacity and packetized data (up to 14.4 kbps).
- **Multiple Access:** Analog systems typically use FDMA, while digital systems use TDMA and CDMA.

### **What are the methods adopted for hand-off procedures?** 

Handoff procedures rely on continuous monitoring of the Received Signal Strength (RSS). The system specifies an optimum signal level (minimum usable signal) for acceptable voice quality at the base station. A slightly stronger signal level is then used as a threshold to initiate the handoff. The MSC determines handoff based on a margin Δ=Pr_handoff​−Pr_minimum_usable​. This margin must be carefully optimized so it is neither too large (causing unnecessary handoffs) nor too small (leading to dropped calls before the handoff completes).

**Part B**

### **Q11 a) Describe the features of the GSM system architecture with the help of a neat block diagram.** _(Note: While the provided text does not contain a specific GSM-labeled block diagram, it provides the fundamental "Overview of Cellular System" architecture which applies to 2G/GSM systems)._ The principal elements of the cellular system architecture include:

- **Base Station (BS) / Base Transceiver Station (BTS):** Located at the approximate center of each cell, it includes an antenna, a controller, and transceivers to communicate on assigned channels with the mobile units.
- **Mobile Telecommunications Switching Office (MTSO) / MSC:** One MTSO serves multiple BSs, usually connected via wireline or microwave links. The MTSO acts as the central coordinator: it connects calls between mobile units, bridges the cellular network to the Public Switched Telephone Network (PSTN), assigns voice channels, performs handoffs, and monitors billing information.
- **Channels:** The architecture utilizes **Control Channels** for call setup and synchronization, and **Traffic Channels** for carrying the actual voice or data between users.

### **Q11 b) How does cell splitting and sectoring improve the capacity and coverage of the cellular system.**

- **Cell Splitting:** Improves capacity by dividing a single congested cell into several smaller cells (microcells). Because each new smaller cell can reuse the system's frequency channels, the overall number of available channels per unit of geographic area increases. Transmitter power is reduced to prevent interference, keeping the frequency reuse plan intact.
- **Cell Sectoring:** Improves capacity by replacing a single omnidirectional antenna with several directional antennas (e.g., three 120∘ sectors or six 60∘ sectors). Because the directional antennas only radiate in specific directions, co-channel interference is drastically reduced. This improves the Signal-to-Interference Ratio (SIR), which allows the system capacity to be increased.

### **Q12 a) Explain the different channel assignment strategies used in cellular system.** To optimize frequency reuse and minimize interference, three main channel assignment strategies are used:

1. **Fixed Channel Allocation (FCA):** Specific channels are permanently allocated to specific cells. If all channels in a cell are occupied, any new call requests are blocked. This system is simple but highly inefficient if the traffic demand across cells is non-uniform.
2. **Dynamic Channel Allocation (DCA):** Channels are pooled together at the Mobile Switching Center (MSC) rather than assigned permanently to cells. When a cell needs a channel, the MSC assigns one dynamically based on a cost-function algorithm (evaluating reuse distance, future blocking probability, etc.). This maximizes channel utilization but requires heavy computational resources.
3. **Hybrid Channel Allocation:** A combination of both fixed and dynamic allocation methods to balance simplicity and efficiency.

### **Q12 b) Enumerate the features of 4G wireless network.** The 4G (IMT-Advanced) wireless network features include:

1. **High Data Rates:** Provides bandwidth higher than 100 Mbps, up to 1 Gbps, enough to support high-quality streaming multimedia content.
2. **All IP Network:** It utilizes an all-packet, IP-based network architecture.
3. **Enhanced Security and Mobility.**
4. **Reduced Latency:** specifically designed for mission-critical applications.
5. **Multimedia capabilities:** Fully supports High Definition (HD) video streaming, gaming, and wearable devices.
6. **VoLTE:** Utilizes Voice over LTE (VoLTE) which relies on IP packets for voice transmission instead of traditional circuit switching


### Here is how **Cell Splitting and Sectoring** are used to improve the capacity and coverage of a cellular system 

#### **Cell Splitting**

- **The Concept:** This involves subdividing a congested, large cell into smaller cells (microcells), each with its own base station and a lower antenna height.
- **The Impact:** It increases the overall system capacity because the same number of channels are reused more frequently over a given geographic area. Because the new cells are smaller, the transmit power of their base stations must be proportionally reduced to prevent interference and maintain the system's frequency reuse plan.

#### **Cell Sectoring**

- **The Concept:** Instead of dividing the cell geographically, this technique replaces a single omnidirectional antenna at the base station with several directional antennas. This divides the cell into "sectors" (typically 120° or 60°).
- **The Impact:** It improves capacity by significantly reducing co-channel interference, which increases the Signal-to-Interference Ratio (SIR). Because the directional antennas only radiate in specific directions, interference from surrounding co-channel cells is drastically cut down.

