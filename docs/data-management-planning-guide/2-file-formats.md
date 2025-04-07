# File Formats
## Introduction
Open data formats are essential for ensuring that research data is accessible, interoperable, and reusable across different systems and platforms. The "R" in FAIR (Findable, Accessible, Interoperable, and Reusable) emphasizes the importance of making data reusable for both humans and machines. By using open, standardized formats, researchers can ensure that their data can be easily shared and integrated with other datasets, enhancing collaboration and supporting long-term research efforts. Open formats foster transparency, enable broader analysis, and allow future users to effectively reuse the data without facing compatibility issues.

## Avoid Proprietary Formats

It's important to prioritise open data formats in your work wherever possible. Proprietary formats introduce additional barriers to the use of the data, and represent a threat to the longevity of the data. Future use of data in these formats requires ongoing support from the companies building the software used to work with the formats. Proprietary formats should be avoided wherever possible. 

Examples of common proprietary formats that should be avoided when sharing and archiving data:

* Matlab files
* XLSX files

## Choosing a File Format

The first step in identifying a suitable file format for your data is to reference the documentation for your chosen data repository. 

1. In the case of generalist data repositories like the [Borealis Repository](../data-repository-documentation/borealis.md), any format is accepted. In cases like this you are encouraged to reference the section below on [Common Open Formats](2-file-formats.md#common-open-formats)
2. In the case of specialized repositories like NCBI, they will often offer specific guidance on suitable formats. Sometimes these repositories may make use of highly specialized formats that are open, but specific to the types of data the repository was designed to handle. Please see the [Data repository documentation](../data-repository-documentation/introduction.md) for more information.

## Common Open Formats

Common widely-used open data formats:

* **CSV** - A widely used format for storing and sharing structured tabular data, CSV is best suited for simple datasets with rows and columns, such as spreadsheets or database exports, and is ideal for interoperability due to its plain-text nature.
* **tabular text files** - These files, often using delimiters like tabs or pipes (e.g., TSV, PSV), are useful for structured data where a delimiter other than a comma is needed to avoid conflicts, making them suitable for datasets with complex text fields.
* **JSON** - A flexible, human-readable format for storing hierarchical or nested data, JSON is commonly used in APIs, web applications, and configurations where relationships between elements need to be preserved.
* **NetCDF files** - Designed for storing multidimensional scientific data, such as climate models, oceanographic measurements, or satellite observations, NetCDF is ideal for large datasets that require efficient storage, metadata support, and advanced querying capabilities.
