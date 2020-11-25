<p align="center">
  <img src="../../../common-assets/blob/main/images/bhasvic/bhasvic-rect-hills-text-small.png?raw=true">
</p>

# Instruction sets <!-- omit in toc -->

## Contents <!-- omit in toc -->

- [What are instruction sets?](#what-are-instruction-sets)
- [Useful resources](#useful-resources)
- [Little Man Computer](#little-man-computer)
- [Assembly vs High-level vs Low-level](#assembly-vs-high-level-vs-low-level)
- [RISC and CISC](#risc-and-cisc)

## What are instruction sets?

An instruction set is a limited set of text instructions that can be used to program a CPU.

Different processor architectures have their own instruction sets, and different Assembly code. The most common are ARM (used in phones and tablets), and AMD64 (64-bit desktop and laptop processors by AMD and Intel).

Assembly language is very efficient as you control exactly what the CPU is doing. For example, the FPS game [.kkrieger](https://en.wikipedia.org/wiki/.kkrieger) is only 96 KB.

## Useful resources

- [Little Man Computer](http://peterhigginson.co.uk/LMC/)
- [LMC Instruction Set](http://www.yorku.ca/sychen/research/LMC/LMCInstructions.html)

## Little Man Computer

Try running this assembly code in the [LMC](http://www.yorku.ca/sychen/research/LMC/LMCInstructions.html)!

```nasm
        INP         /* Get input */
        STA A       /* Store input in accumulator */
LOOP    LDA A       /* Begin loop / load value from accumulator into register A */
        OUT
        SUB ONE
        STA A
        BRZ ENDTHIS
        BRA LOOP
ENDTHIS LDA A
        SUB A
        OUT
        HLT
A       DAT
ONE     DAT 1
```

When you press **Assemble into RAM**, you can see that the the Assembly code is assembled, then stored into RAM. Then hit **Run**.

The textual instructions are converted into numeric values. For example `INP` is turned into `901`.

The blue blobs are data being returned from or sent to RAM. The red blobs are the registers being accessed.

## Assembly vs High-level vs Low-level

Assemby language requires many more lines of code than high or low level programming languages.

In Assembly, a simple algorithm to sort a list of numbers can take up to 50 lines, compared to about 20 lines in C (high-level language), or just 5 in Python (high-level language).

High-level languages can fit multiple lines of assembly into a single line of their high-level language.

**High-level languages work on many systems.** It is up to the compiler to convert the source code into an executable binary for each architecture.

## RISC and CISC

**Reduced Instruction Set Computer**

- Simpler hardware
- More complex to code
- Each instruction is only one CPU cycle
- Lower energy consumption
- Used in ARM processors
- Physically smaller (due to less complex circuitry), so less silicon needed to produce the processors
- Enters a sleep mode when not actively processing

**Complex Instruction Set Computer**

- More complex (and expensive) hardware
- Easier to code for
- Multiple instruction cycles per instruction
- Greater energy consumption
- Used in AMD and Intel processors
- Physically larger, so more silicon needed to produce the processors
