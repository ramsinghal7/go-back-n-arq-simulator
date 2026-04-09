# Go-Back-N ARQ Simulator

An interactive, browser-based simulator that demonstrates the Go-Back-N Automatic Repeat reQuest (ARQ) protocol used for reliable data transmission over unreliable channels.

This simulator visually shows how frames are sent, acknowledged, lost, and retransmitted in real-time.

## Features

- **Animated sender and receiver nodes**
  - Sliding send/receive windows
  - Buffer visualization
  - Acknowledged frame area
- **Configurable parameters**
  - Window size (N)
  - Loss probability for frames and ACKs
  - Simulation speed (Slow → Very Fast)
  - Total number of frames to send
- **Real-time statistics**
  - Frames sent
  - Frames lost
  - Retransmissions
- **Event log**
  - Timestamped events for:
    - Frame sent / received
    - Frame loss
    - ACK sent / received
    - Timeouts and Go-Back-N retransmissions
- **Visual legend**
  - Colors for ready, sent, acknowledged, lost, and retransmitted frames

## Getting Started

### 1. Run locally

You can simply open `index.html` in a modern browser (Chrome, Firefox, Edge, etc.):

- Double-click `index.html`, or
- Right click → “Open With” → your browser

No backend or build step is required.

> Note: For best results, use a desktop browser; the layout is responsive but the visualization is clearer on larger screens.

## How to Use the Simulator

1. **Adjust parameters** in the *Simulation Controls* panel:
   - **Window Size (N)**: number of frames that can be sent before waiting for ACKs.
   - **Loss Probability (%)**: chance that a frame or ACK is lost.
   - **Simulation Speed**: how quickly frames/ACKs move.
   - **Frames to Send**: total number of frames to transmit in this run.
2. Click **“Start Simulation”**.
3. Watch the:
   - Sender’s **send window** and **buffer** scroll through sequence numbers.
   - Frames move along the **transmission line**.
   - Receiver’s **receive window** and **acknowledged** area fill up.
   - **Event log** update with detailed protocol events.
4. Click **“Reset”** to stop and clear the current run, and **“Clear Log”** to just clear the log messages.

## What It Demonstrates

- Sliding window mechanism of Go-Back-N ARQ.
- In-order delivery requirement at the receiver (out-of-order frames are discarded).
- Impact of frame/ACK loss on throughput.
- Timeout and Go-Back-N retransmission behavior:
  - On timeout, all unacknowledged frames from the base sequence number are retransmitted.

## Technologies Used

- **HTML5** for structure
- **CSS3** (with simple animations) for layout and visualization
- **Vanilla JavaScript** for simulation logic and DOM updates
- **Font Awesome** (CDN) for icons

## Possible Improvements

- Add support for selective repeat ARQ for comparison.
- Display a timeline or graph of throughput vs. loss probability.
- Allow step-by-step (manual) mode in addition to automatic simulation.
- Add explanations/tooltips for each event in the log.
