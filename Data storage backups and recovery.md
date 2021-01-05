<p align="center">
  <img src="https://github.com/davwheat-bhasvic/common-assets/blob/main/images/bhasvic/bhasvic-rect-hills-text-small.png?raw=true">
</p>

<!-- omit in toc -->

# Data storage, backups, and recovery <!-- omit in toc -->

## Contents <!-- omit in toc -->

- [Network attached storage (NAS)](#network-attached-storage-nas)
  - [Advantages](#advantages)
  - [Disadvantages](#disadvantages)
- [Cloud storage](#cloud-storage)
  - [Advantages](#advantages-1)
  - [Disadvantages](#disadvantages-1)
- [RAID (Redundant array of independent disks)](#raid-redundant-array-of-independent-disks)
  - [RAID levels](#raid-levels)
    - [Data striping](#data-striping)
    - [Data mirroring](#data-mirroring)
- [Storage Area Network (SAN)](#storage-area-network-san)
- [Backups](#backups)
  - [Types of backup](#types-of-backup)
    - [Full backup](#full-backup)
    - [Incremental backup](#incremental-backup)
    - [Differential backup](#differential-backup)
- [Data recovery](#data-recovery)
- [Backup and restore procedures](#backup-and-restore-procedures)

## Network attached storage (NAS)

NAS is where you attach storage media (hard drives, solid state drives, etc) to a network. This is so that multiple users or devices can share a central storage repository. The storage usually shows as a network drive, and can be an alternative to cloud storage.

### Advantages

- easy to share files between multiple users
- can access your own files on multiple different devices
- popular for backup and recovery purposes
  - automated backups of local data to a NAS is common

### Disadvantages

- permissions must be configured correctly to prevent unauthorised access

## Cloud storage

Cloud storage is a virtual place where you can store data. The data is stored in a server (or multiple servers) which is owned and run by the cloud storage provider.

This cloud storage can be accessed from any location with access to the internet.

### Advantages

- easy to access from many locations
- often provide sharing options

### Disadvantages

- you need to rely on cloud provider to keep your data safe
- cannot access data without an internet connection


## RAID (Redundant array of independent disks)

RAID is technology used to store data spanning across multiple physical disks. These multiple disks are combined together in either hardware or software to show in the Operating System as a single logical disk.

RAID can be configured for redundancy (RAID 1), speed (RAID 0), or both (RAID 10). In configurations with redundancy, there are multiple copies of the same data on multiple physical disks so that, if a drive fails, the RAID array can be rebuilt from the other copy/copies available on other disks.

RAID can combine disks to create...

- a very large storage area,
- a very fast storage area (RAID 0),
- a very fault-tolerant storage area (RAID 1),
- or a combination of these (RAID 10, RAID 40, etc)

### RAID levels

Different RAID levels exist. These levels usually offer data striping or data mirroring, or a combination of the two.

#### Data striping

Data striping is where data is divided into multiple blocks across multiple disks to allow for reading and writing data simultaneously to multiple disks.

#### Data mirroring

Data mirroring stores a copy of the data on the drive on multiple disks. This ensures that, if a drive fails, the contents can still be accessed.

## Storage Area Network (SAN)

A SAN is a high-speed network that connects storage devices with servers. It provides block-level data storage where each block can be controlled as an individual disk, and these blocks are managed by a server operating system.

SANs are usually used to access storage devices, such as disk arrays or tape libraries. These devices appear to the operating system as direct-attached storage. SANs usually consist of a dedicated network of storage devices which can't be accessed from the LAN (it's a separate network).

## Backups

Backups are copies of data kept in a separate location to prevent loss of data.

Data can be lost for many reasons, including...

- human error
- physical damage (fire, natural disasters, etc)
- malware

Backups are often kept in cloud storage, or in a completely different location (called an off-site backup). A copy of a file in another place on the same disk is not good enough: if the disk fails, both copies are lost.

### Types of backup

There are many different types of backup.

#### Full backup

This involves a full copy of all your data

**Pros**

- excellent protection

**Cons**

- time consuming
- requires large amounts of storage capacity

#### Incremental backup

This checks for changes between the previous backup and the current file state, and just backs these up.

**Pros**

- quick
- requires less storage

**Cons**

- more complex to restore

#### Differential backup

A full backup is done first, and subsequent backups store the specific changed made since the last full backup. New differential backups build off the last full backup, not the last differential backup.

**Pros**

- moderately fast
- easy to restore from
- less storage needed than a full backup

**Cons**

- slower to restore than a full backup

## Data recovery

Data recovery is similar to losing a lovingly made album of photos, and being handed a pile of photos and being asked to recreate the album.

A backup and restore solution should, not only store the data, but also the file structure, metadata, and more.

## Backup and restore procedures

- tests should be performed regularly to ensure they work as expected if any data is actually lost
- an organisation losing their central server could be devastating for productivity
