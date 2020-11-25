<p align="center">
  <img src="../../../common-assets/blob/main/images/bhasvic/bhasvic-rect-hills-text-small.png?raw=true">
</p>

# Performance factors <!-- omit in toc -->

## Contents <!-- omit in toc -->

- [Why is CPU performance important?](#why-is-cpu-performance-important)
- [Factors that affect execution speed](#factors-that-affect-execution-speed)
  - [Pipelining](#pipelining)
  - [Number of cores](#number-of-cores)
  - [Clock speed](#clock-speed)
  - [Cache memory](#cache-memory)
  - [RAM speed](#ram-speed)
  - [Amount of RAM](#amount-of-ram)
  - [Cooling](#cooling)
  - [Motherboard design](#motherboard-design)
  - [Word length](#word-length)
- [How can we increase execution speeds?](#how-can-we-increase-execution-speeds)
- [Research task: suggesting computers hardware for scenarios](#research-task-suggesting-computers-hardware-for-scenarios)
  - [Scenario 1](#scenario-1)
    - [CPU](#cpu)
    - [Motherboard](#motherboard)
    - [RAM](#ram)
    - [Storage](#storage)
    - [Case](#case)
  - [Scenario 2](#scenario-2)

## Why is CPU performance important?

Execution speed is basically how fast software can run on a computer system.

With faster execution speeds...

- your software will run faster
- your system will be more responsive
- your computer will have a greater user experience
- resulting in greater productivity

All software has a set of minimum required system specifications. If the computer is below this specification, the software may not run correctly or at all.

E.g. a modern AAA game running on a 5 year old laptop. It won't work! (Or if it does, it'll be ridiculously slow.)

## Factors that affect execution speed

### Pipelining

Pipelining allows a CPU to begin fetching the next instruction while the previous is decoding, and allows an instruction be fetched and another decoded while a third is being executed.

This allows CPUs to execute instructions faster as they don't need to wait for the previous instruction to complete before beginning the next.

### Number of cores

Multi-core processors allow multiple different instructions to be executed at once.

This saved a lot of time during heavy workloads, as one core could be dedicated to handling background tasks in the OS, while another is dedicated to handling the active application, for example.

### Clock speed

The clock speed is the speed at which components within the CPU run. Each clock cycle results in one step in the Fetch-Decode-Execute cycle.

If the clock speed of a CPU is higher, it means the Fetch-Decode-Execute cycle executes faster, resulting in instructions completing faster.

### Cache memory

Often, a big bottleneck of modern CPUs is the speed at which data can be fetched from RAM. If this takes too long, it means that the CPU core(s) are sitting idle instead of processing the instruction.

Cache allows for copies of the contents of often accessed RAM addresses to be kept close to the CPU in much faster memory. This means the CPU can fetch instructions and data much faster than it could if it was using RAM.

CPUs usually have several cache memory levels. The lower numbered levels (e.g. L1) are much faster, but also much smaller and more expensive than the higher numbered levels (e.g. L3).

### RAM speed

The CPU relies on RAM (main memory) for fetching the next instruction(s) to be executed, and the data to perform those instructions on.

If the RAM is faster, it means the CPU can access the data stored within it much faster, reducing the amount of time that the CPU is idling for.

### Amount of RAM

If you have more RAM, it means more data and instructions can be held at one time, meaning that the computer doesn't need to refer back to secondary storage to 'refetch' the data or instructions.

If you have too little RAM, the computer needs to continuously swap data and instructions in and out of RAM very often.

Modern computers usually have 8 GB RAM, but 16 GB is seen as a recommended amount for multitasking.

### Cooling

CPUs are often limited by temperature. When CPUs execute many instructions, the CPU will use more power, generating much more heat.

This heat can cause the CPU to fail more quickly, so heatsinks and cooling fans are very important for CPUs to run efficiently.

If a CPU gets too hot, it will thermal throttle, meaning the CPU slows down. If it becomes critically hot (T-Junction), the computer will shut down immediately.

### Motherboard design

Motherboards often support different versions of processors and memory, etc.

All components are connected to the motherboard. If the motherboard doesn't support the same systems or versions as its components, it can limit the speeds.

E.g. if the CPU supports PCI-e 3.0 x16, but the motherboard only supports PCI-e 3.0 8x, then the PCI-e bus will be limited to half of its theoretical speed.

### Word length

Word length is the amount of data a CPU can process simultaneously. A larger word length means that more data can be processed in the CPU at a faster rate. Modern CPUs have a word length of 64, so they are commonly referred to as '64 bit processors'.​​

The 'bits' refers to the amount of instructions the CPU can fetch and process at once. A 64 bit processor can fetch 64 bits of instructions at a time.

Word length is especially important in floating point calculations. Increasing the word length does not directly affect the performance of a system, but when very large numbers, or numbers with many decimal places, are being processed, the calculations can be completed with fewer instructions (sometimes just 1), instead of having to break them up into multiple different instructions. This is especially true with more modern instruction sets in computers, such as AVX and AVX2.​

Normal consumers most likely won't notice this, but when applications need to perform these calculations, it means they can finish much faster than they would normally.

## How can we increase execution speeds?

- Overclocking
  - Overclocking allows us to increase the clock speed of our processors above the base speeds, at the expense of more heat and power and possible instability.
- Adding more and faster RAM
  - Adding more RAM means the system doesn't have to refer back to secondary storage as often, meaning that
- New CPU
  - May have more cores, faster clock speed, more cores, more cache memory, or contain more efficient implementations of the instruction set.
- Parallel processing
  - Pipelining, multi-processing or multi-threading

## Research task: suggesting computers hardware for scenarios

**Suggest and computer for each of the people below, including the cost. Use any site you'd like to source hardware that will work effectively whilst minimising costs. You need to justify your answers.**

### Scenario 1

> **A user who works from home using Google Docs, using a web browser to do this.**

| Type        | Item                                                      | Price                    |
| ----------- | --------------------------------------------------------- | ------------------------ |
| CPU         | AMD Ryzen 3 3200G 3.6 GHz Quad-Core Processor             | £80.99 @ Currys PC World |
| Motherboard | Asus PRIME B450M-A Micro ATX AM4 Motherboard              | £57.27 @ CCL Computers   |
| Memory      | Patriot Viper Steel 8 GB (1 x 8 GB) DDR4-3200 CL16 Memory | £32.50 @ CCL Computers   |
| Storage     | Western Digital Blue 250 GB M.2-2280 Solid State Drive    | £36.26 @ BT Shop         |
| Case        | Xigmatek Scorpio MicroATX Mid Tower Case                  | £24.52 @ Ebuyer          |
|             | Total                                                     | £231.54                  |
|             | Generated by PCPartPicker 2020-10-21 15:22 BST+0100       |                          |

[PCPartPicker list](https://uk.pcpartpicker.com/list/Mv8hqp)

#### CPU

The 3200G is a quad-core processor, which is easily enough for basic web browsing and using Google Docs. It supports overclocking (most likely doesn't make a difference in this scenario), and also boosts up to almost 4 GHz, if temperature allows.

The stock heatsink is fine, but a 3rd party would be better.

#### Motherboard

A basic motherboard is all that is needed in this situation. No overclocking will be done, so no beefy VRMs and heatsinks are needed. Micro-ATX allows me to choose a smaller case, which is best for a simple PC like this.

#### RAM

8 GB is enough for basic web browsing but, if budget allows, going to two 8 GB sticks in dual channel would be better.

Ryzen loves fast RAM, so 3200 MHz XMP RAM is a minimum. The CAS latencies are also low, which is important for Ryzen, too.

#### Storage

A fast SSD was chosen to provide consistent responsiveness in the system and fast boot times. Since the person works from home using cloud storage (Google Docs) storage capacity isn't a big issue. If needed, they could purchase a 1 TB HDD for about £35.

#### Case

A simple, elegant case which has good reviews and looks.

### Scenario 2

> **A local business with 1000 employees that needs a new file server for them to upload and access business documents from.**

| Type                  | Item                                                          | Price                  |
| --------------------- | ------------------------------------------------------------- | ---------------------- |
| CPU                   | AMD Ryzen 9 3900X 3.8 GHz 12-Core Processor                   | £414.98 @ Aria PC      |
| Motherboard           | MSI MAG B550 TOMAHAWK ATX AM4 Motherboard                     | £159.95 @ AWD-IT       |
| Memory                | Corsair Vengeance LPX 32 GB (2 x 16 GB) DDR4-3600 CL18 Memory | £133.58 @ Amazon UK    |
| Storage               | Samsung 970 Evo 500 GB M.2-2280 NVME Solid State Drive        | £72.99 @ CCL Computers |
| Storage               | Western Digital Red 4 TB 3.5" 5400RPM Internal Hard Drive     | £91.58 @ Senetic       |
| Storage               | Western Digital Red 4 TB 3.5" 5400RPM Internal Hard Drive     | £91.58 @ Senetic       |
| Storage               | Western Digital Red 4 TB 3.5" 5400RPM Internal Hard Drive     | £91.58 @ Senetic       |
| Storage               | Western Digital Red 4 TB 3.5" 5400RPM Internal Hard Drive     | £91.58 @ Senetic       |
| Storage               | Western Digital Red 4 TB 3.5" 5400RPM Internal Hard Drive     | £91.58 @ Senetic       |
| Wired Network Adapter | Asus XG-C100C PCIe x4 10 Gbit/s Network Adapter               | £83.37 @ CCL Computers |
|                       | Total                                                         | £1322.77               |
|                       | Generated by PCPartPicker 2020-10-21 15:43 BST+0100           |                        |
