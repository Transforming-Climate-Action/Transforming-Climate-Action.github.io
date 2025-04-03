# Data Backup 

## Introduction
Backing up research data is a critical part of responsible data management. It safeguards valuable information against loss, corruption, and ensures the continuity and reproducibility of research. Effective backup strategies help researchers meet institutional, ethical, and funder requirements for data security and preservation. Backups are also essential to the FAIR data principles—particularly in making data Accessible and Reusable over time. Without backups, data can become permanently lost or inaccessible, undermining long-term stewardship and reuse. This guide outlines best practices for backing up different types of research data, including raw data, processed files, documentation, and metadata, using reliable and sustainable storage solutions throughout the research data lifecycle.


## Why Back Up Your Data?

 - Prevent data loss due to hardware failure, human error, or cyberattacks
 - Sport reproducibility and long-term research access
 - Comply with funder or institutional policies

we strongly suggest that each DMP include storage and backup during the research process.

## What data you should backup 

 - Raw data (e.g. experimental results, survey responses)
  - - All incoming data should be preserved as received, to serve as a reference if questions arise later. 
 - Processed data (e.g. cleaned datasets, code outputs)
 - Code/scripts used for analysis/processing
   - - We recommend using code repositories (e.g., GitHub, GitLab) to store code and track versions securely.
 - Documentation (e.g. README files, codebooks, data dictionaries)
 - [Metadata](data-management-planning-guide/documentation-and-metadata.md) and project notes


## Where to Back Up

- **Storage Media**: Use a combination of storage media to reduce risk and increase redundancy:
    - **Institutional servers**: Managed and backed-up by your organization or research institution.
    - **External hard drives**: Portable and easy to use, but should be encrypted and stored securely.
    - **Cloud storage services**: Reliable and accessible from anywhere (e.g., OneDrive, Google Drive, Dropbox).
    - **Network-attached storage (NAS)**: Shared drives suitable for collaborative teams or labs.

## How Often to Back Up

- **During Active Research**: Back up data daily or immediately after significant changes or new data collection.
- **For Stable Data**: Perform weekly or biweekly backups for datasets that do not change frequently.


## How to Back Up Data

A reliable backup strategy is essential for preserving the integrity and availability of your research data. The most widely recommended approach is the 3-2-1 Backup Rule, which offers a simple and effective way to safeguard against data loss.

**Follow these steps to back up your data effectively:**


1.  **Organize Your Data**

    - Define a clear [file naming convention](file-naming-convention.md) (e.g., projectName_date_version.ext) and follow it consistently throughout your project.

    - Separate raw, processed, and documentation files clearly.

2.  **Apply [the 3-2-1 Backup Rule](3-2-1-data-backup-strategy.md)**

3.  **Use Automation When Possible**
    - Set up scheduled backups using tools to minimize manual errors.

4.  **Document Your Backup Plan**
    - Maintain a record of where each copy is stored, who is responsible, and how frequently backups occur.

5.  **Test and Review**
    - Periodically verify that backups are working and data can be restored.
    - Update your strategy as your data grows or research needs change.


!!! note
    The TCA Data Management Accelerator is available to assist with creating and implementing backup strategies. They also provide free cloud storage services locations for your research data backups.




