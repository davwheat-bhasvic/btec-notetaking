<p align="center">
  <img src="https://github.com/davwheat-bhasvic/common-assets/blob/main/images/bhasvic/bhasvic-rect-hills-text-small.png?raw=true">
</p>

# Error correction <!-- omit in toc -->

## Contents <!-- omit in toc -->

- [What is error correction](#what-is-error-correction)
- [Automatic repeat requests (ARQ)](#automatic-repeat-requests-arq)
  - [Implications](#implications)
  - [Variants](#variants)
    - [Stop-and-wait ARQ](#stop-and-wait-arq)
      - [Implications](#implications-1)
    - [Go-back-n ARQ](#go-back-n-arq)
      - [Implications](#implications-2)
    - [Selected repeat ARQ](#selected-repeat-arq)
      - [Implications](#implications-3)
- [Forward Error Correction (FEC)](#forward-error-correction-fec)
  - [Uses of FEC](#uses-of-fec)
  - [Implications](#implications-4)

## What is error correction

Error correction is used to recover data after an error is detected through error detection.

Error correction algorithms fall into two categories:

- retransmit the data if an error is detected
  - Automatic repeat requests (ARQ)
- ways to fix the errors without retransmitting
  - Forward error correction (FEC)

## Automatic repeat requests (ARQ)

If a packet is received and an error is detected, it will be retransmitted.

A retransmission can be triggered by one of two things:

- an acknowledgment of an error in a packet is sent (NACK), or
- no acknowledgment of the packet (ACK) is received within a specified time period

### Implications

- ARQ is used for TCP requests over the internet
- ARQ has delays while waiting for timeouts
- Requires a two-way communication channel
- Buffers to hold received packets while waiting for the rest/retransmitted ones

### Variants

Three variants of ARQ exist:

- stop-and-wait ARQ
- go-back-n ARQ
- selective repeat ARQ

#### Stop-and-wait ARQ

1. **SENDER:** transmits a packet
2. **SENDER:** waits a specified time (a timeout)
3. **RECEIVER:** if a packet is successfully received, send an ACK message; if an error is detected, discard packet
4. **SENDER:** if no ACK received, retransmit packet; if ACK received, send next packet

##### Implications

- slow
  - only one packet can be sent at a time
- each packet is sent in order
  - if one packet fails to be received multiple times, the other packets are never received

#### Go-back-n ARQ

1. **SENDER:** sends all packets, with packet numbers, without waiting for ACK
2. **RECEIVER:** if packet with error is received, it will send an ACK with the latest successful packet number
3. **RECEIVER:** discard damaged packets
4. **SENDER:** looks at ACKs and resends all packets with packet numbers above the last ACK received

##### Implications

- requires two-way communication
- faster than stop-and-wait
  - all packets are sent without waiting for ACKs

#### Selected repeat ARQ

1. **SENDER:** sends all packets, with packet numbers, without waiting for ACK
2. **RECEIVER:** sends ACK for every packet it successfully receives (with packet number)
3. **RECEIVER:** discards damaged packets
4. **SENDER:** looks at ACKs and resends all packets where ACK has not been received
5. **RECEIVER:** uses packet numbers to rebuild the data from all the packets

##### Implications

- requires two-way communication
- requires a buffer to store all packets
- only missing/damaged packets are re-sent

## Forward Error Correction (FEC)

- an error correction code (ECC) is sent within the frame
- when the frame is received, the ECC is analysed to detect errors and make corrections
- bad data is automatically rebuilt
- ECC is removed before data is rebuilt

### Uses of FEC

- where transmissions are vulnerable to corruption
- where retransmission would result in limited transfer speeds
  - e.g. WiFi, mobile data, satellites
- where stability and reliability is critical
  - e.g. server ECC RAM

### Implications

- redundant data is sent
- no retransmission required
- sophisticated techniques (incl. repetition and parity) is used
