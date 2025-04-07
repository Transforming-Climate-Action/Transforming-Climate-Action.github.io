# Data Backup Strategy

## **_Introduction_**
Backing up research data is a critical part of responsible data management. It safeguards valuable information against loss, corruption, and ensures the continuity and reproducibility of research. Effective backup strategies help researchers meet institutional, ethical, and funder requirements for data security and preservation. Backups are also essential to the FAIR data principles—particularly in making data Accessible and Reusable over time. Without backups, data can become permanently lost or inaccessible, undermining long-term stewardship and reuse. This guide outlines best practices for backing up different types of research data, including raw data, processed files, documentation, and metadata, using reliable and sustainable storage solutions throughout the research data lifecycle.

## **_How to Back Up Data_**

A reliable backup strategy is essential for preserving the integrity and availability of your research data. The most widely recommended approach is the 3-2-1 Backup Rule, which offers a simple and effective way to safeguard against data loss.

**Follow these steps to back up your data effectively:**


1.  **Identify Data to Back Up**
  
    - Determine which types of data are essential to back up. This typically includes raw data, processed data, analysis results, documentation, and metadata.
    - Organize and label your files clearly so that critical data is easy to identify and locate. For more guidance, see the [file-naming-convention](file-naming-convention.md) for more details.

2.  **Apply [the 3-2-1 Backup Rule](the-3-2-1-data-backup-strategy.md)**

3.  **Automate and Schedule Regular Backups**
    - Set up automated backups using tools to reduce the risk of manual errors.
    - Back up your data according to the nature of your work: daily during active data collection or analysis, and weekly or biweekly for more stable datasets.

4.  **Document Your Backup Plan**
    - Maintain a record of where each copy is stored, who is responsible, and how frequently backups occur.

5.  **Test and Review**
    - Periodically verify that backups are working and data can be restored.
    - Update your strategy as your data grows or research needs change.


!!! note
    The TCA Data Management Accelerator is available to assist with creating and implementing backup strategies. They also provide free cloud storage services locations for your research data backups.

## **_Example Plan_**

When data—including metadata, raw data, and processed data—is collected by the field team, it is first uploaded to the group’s lab computer.

- The data is backed up daily to an external hard drive for local redundancy.
- Simultaneously, a third-party software tool automates the daily transfer of new data to a remote VPS hosted by the Digital Research Alliance of Canada for secure off-site backup.