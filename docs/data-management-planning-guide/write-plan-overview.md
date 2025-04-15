# DMP Asisstant - Write Plan Overview

This section in the DMP Assistant represents the core of your data management plan. There are a number of key considerations that can greatly strengthen your data management plan. Wherever possible, additional information and recommendations are provided for each of the sections described below.

If you haven't initiated your data management plan in the DMP Assistant yet, please see [Starting a Data Management Plan](starting-a-data-management-plan.md)

**If you haven't yet decided which data repositories you're planning to use for your datasets you should consider making that choice before developing your data management plan.** In many cases(such as metadata standards), your chosen data repository will dictate your answers.

For support choosing a data repository please visit [Choosing a Repository](../data-repository-documentation/introduction.md#choosing-a-repository)

## Project Outputs

![DMP Assistant - Project Outputs](../img/dmp-guide/dmp-project-outputs.png)

### What data will you collect, and what research outputs will you create?

The goal in this section of the data management plan is to identify the key outputs of this research. This includes: datasets, software, code, samples, theses, images, video, graphs, models, publications, and anything else you feel is relevant.

### Do your research outputs contain Essential Ocean Variables (EOVs) or Essential Climate Variable (ECVs)?

This section also asks about Essential Ocean Variables (EOVs) and Essential Climate Variables (ECVs). EOVs and ECVs are being used by the global ocean data management community to identify priority datatypes for global interoperability and availability in support of collaboration. CIOOS provides an overview of EOVs here: [Essential Ocean Variables](https://cioos.ca/essential-ocean-variables/). An overview of ECVs is available here: [Essential Climate Variables](https://gcos.wmo.int/site/global-climate-observing-system-gcos/essential-climate-variables)

### What file formats will your research outputs be in?

For recommendations and more information please see the [File Formats](file-formats.md) page.

## Documentation and Metadata

![DMP Assistant - Documentation and Metadata 1](../img/dmp-guide/dmp-documentation-and-metadata-1.png)
![DMP Assistant - Documentation and Metadata 2](../img/dmp-guide/dmp-documentation-and-metadata-2.png)

For recommendations and more information about choosing a metadata standard, please see the [Documentation and Metadata](documentation-and-metadata.md)

## Storage and Backup

![DMP Assistant - Storage and Backup 1](../img/dmp-guide/dmp-storage-and-backup-1.png)
![DMP Assistant - Storage and Backup 2](../img/dmp-guide/dmp-storage-and-backup-2.png)

### How and where will your research outputs be stored and backed up during the active phase of the research project?

For recommendations and more information on how to back up your research outputs, please see the [Data Backup Strategy](backup-strategy.md).

<!-- prettier-ignore -->
!!! note
    If safe, secure, redundant near-term data storage represents a gap in your project, it is encouraged that you submit an [Application for the Canadian Digital Research Alliance Rapid Access Service.](https://docs.google.com/forms/d/e/1FAIpQLSeU_BoRk5cEz3AvVLf3e9yZJq-OvcFCQ-mg7p4AWXmUkd5rTw/viewform) For data storage requirements up to 10 terabytes applications are typically processed very quickly. [Additional details available here.](https://www.alliancecan.ca/en/services/advanced-research-computing/accessing-resources/rapid-access-service) If you have any questions please reach out to the data management accelerator at [insert address]

### What collaboration environment and procedures will the research team use to access, modify and contribute data or other research outputs throughout the active phase of the project? How will you organize, name and version-control files in a (shared) directory?

For recommendations and more information about how to name your files, please see the [File Naming Convention](file-naming-convention.md).

<!-- prettier-ignore -->
!!! note
    If transfer of large data files represents a challenge in your project, the Canadian Digital Research Alliance offers a robust data transfer service for large data files. Combined with the Rapid Access Service documented above, this represents a robust approach to the transfer and storage of small to medium volumes of data. [Additional details available here.](https://docs.alliancecan.ca/wiki/Globus) If you have any questions please reach out to the data management accelerator at [insert address]

### VALERIA - Laval University Storage Solution

[VALERIA](https://valeria.science/accueil) is Laval University's institutional storage platform that integrates with the Canadian Digital Research Alliance infrastructure. Among others, it offers:

- Secure and user-friendly platform for file sharing and collaboration
- 4 terabytes of subsidized storage space per researcher
- Built-in version control and file synchronization
- Integration with common research tools and workflows

VALERIA is available to all Laval University researchers and their collaborators. For detailed information about features, setup guides, and best practices, visit the [VALERIA documentation website](https://doc.s3.valeria.science/fr/index.html).

## Preservation

![DMP Assistant - Preservation](../img/dmp-guide/dmp-preservation.png)

<!-- prettier-ignore -->
!!! note
    Data and metadata may be preserved through submission to a suitable open data repository. Please see the [Data Repository Documentation](../data-repository-documentation/introduction.md) for further details.

## Sharing and Reuse

![DMP Assistant - Sharing and Reuse 1](../img/dmp-guide/dmp-sharing-and-reuse-1.png)
![DMP Assistant - Sharing and Reuse 2](../img/dmp-guide/dmp-sharing-and-reuse-2.png)

CIOOS provides detailed descriptions and in some cases examples for these questions.

If you plan to make your data open it is beneficial to adopt a formal open data license to ensure that you are appropriately attributed when others use your data and to ensure that your data are used in ways you're comfortable with. For more information please see [Open data Licenses](open-licensing.md).

If you're planning to release a dataset that others could benefit from, consider writing a [data paper](../data-repository-documentation/data-papers.md) to help raise awareness and encourage reuse.

## Responsibilities and Resources

![DMP Assistant - Responsibilities and Resources](../img/dmp-guide/dmp-responsibilities-and-resources.png)

### Example Data Management Workflow

```mermaid
flowchart TD
    subgraph DC[Data Collection]
        A1[Initial data collection]
        A2[Metadata capture]
    end

    subgraph ODM[Operational Data Management]
        B1[Convert data into usable format]
        B2[Record metadata into a file]
        B3[Store & organize data]
        B4[Create backup of data]
        B5[Apply automated QA/QC pipeline]
    end

    subgraph MDM[Master Data Management]
        C1[Convert data into standard format]
        C2[Convert metadata into standard format]
    end

    DC --> ODM
    ODM --> MDM

    %% Data Collection flow
    A1 --> A2

    %% Operational Data Management flow
    B1 --> B2
    B2 --> B3
    B3 --> B4
    B4 --> B5

    %% Master Data Management flow
    C1 --> C2
```

### Key Roles and Responsibilities

| Role                        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Responsible for data        | The person on your team who is responsible for your data. This is the person who will liase with the data management accelerator                                                                                                                                                                                                                                                                                                                                      |
| Operational data management | The people who will carry out your operational data management. This includes: conversion of data into a usable format, naming, organization, and storage of the data, backup of the data, QA/QC of the data. These roles may be split between members of your team and your institutional data manager. If you plan to share these roles with your institutional data manager this section should be developed in collaboration with the institutional data manager. |
| Master data management      | This represents the work to standardize your data and prepare it for long-term archival, or submission to an open data repository. If desired, this work can be supported by the Data Management Accelerator. If you plan to request support from the Data Management Accelerator this secction should be developed in collaboration with your institutional data manager.                                                                                            |

<!-- prettier-ignore -->
!!! note
    The TCA Data Management Accelerator is here to support you throughout the data management process, but ultimate responsiblity for your datasets should remain within your team.

- Who will be responsible for managing this project's research outputs during and after the project? Please list the data management-specific tasks for which project contributors will be responsible.

<!-- prettier-ignore -->
!!! note
    For more detail on the ways that the TCA Data Management Accelerator can support you please see [Data Management Accelerator Support](DMA-support.md)

- How will responsibilities for managing data activities be handled if substantive changes happen in the personnel overseeing the project's data, including a change of Principal Investigator?
- What resources will you require to implement the management of your research outputs? What do you estimate the overall cost for this to be?

## Ethics and Legal Compliance

![DMP Assistant - Ethics and Legal Compliance 1](../img/dmp-guide/dmp-ethics-and-legal-compliance-1.png)
![DMP Assistant - Ethics and Legal Compliance 2](../img/dmp-guide/dmp-ethics-and-legal-compliance-2.png)

- Who owns the intellectual property of the research outputs, and how will that person or institution manage legal, ethical, and intellectual property issues?
- Does your project include Indigenous partner involvement, and if so, does it follow the CARE and OCAP Principles?
- If your research project includes sensitive or restricted data, how will you ensure intellectual property rights are protected and that sensitive or restricted data is securely managed and accessible only to approved members of the project, during the active phase of the research?
- If applicable, what strategies will you undertake to address secondary uses of sensitive data?

# Additional DMP Considerations for Sensitive Data

## Sharing and Reuse

- What data cleaning and anonymization procedures will be required to protect the confidentiality of partitipants in your research?

More detailed documentation is available through the [DMP Assistant website](https://dmp-pgd.ca/), which is built and maintained by the [Digital Research Alliance of Canada](https://alliancecan.ca/en).
