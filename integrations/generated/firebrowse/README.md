# @datafire/firebrowse
A simple and elegant way to explore cancer data

## Operation: All
This service provides access to the Gistic2 all_data_by_genes.txt output data. This data is a gene-level table of copy number values for all samples. The returned copy number values are in units (copy number - 2) so that no amplification or deletion is 0, genes with amplifications have positive values, and genes with deletions are negative values. The data are converted from marker level to gene level using the extreme method: a gene is assigned the greatest amplification or the least deletion value among the markers it covers. Results may be filtered by cohort, gene, or barcode, but at least one gene or barcode must be supplied.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "gene": {
      "type": "array",
      "description": "Comma separated list of gene name(s)."
    },
    "tcga_participant_barcode": {
      "type": "array",
      "description": "Comma separated list of TCGA participant barcodes (e.g. TCGA-GF-A4EO)."
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "tcga_participant_barcode",
        "cohort",
        "gene"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Amplified
This service provides access to the Gistic2 amp_genes.conf_99.txt output data.  At least 1 gene or cohort must be supplied.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "gene": {
      "type": "array",
      "description": "Comma separated list of gene name(s)."
    },
    "q": {
      "type": "number",
      "description": "Only return results with Q-value <= given threshold.",
      "maximum": 1
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "q",
        "cohort",
        "gene"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Deleted
This service provides access to the Gistic2 del_genes.conf_99.txt output data.  At least 1 gene or cohort must be supplied.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "gene": {
      "type": "array",
      "description": "Comma separated list of gene name(s)."
    },
    "q": {
      "type": "number",
      "description": "Only return results with Q-value <= given threshold.",
      "maximum": 1
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "q",
        "cohort",
        "gene"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Focal
This service provides access to the Gistic2 focal_data_by_genes.txt output data. This output is similar to the all_data_by_genes.txt output, but using only focal events with lengths greater than the  focal length cutoff. This data is a gene-level table of copy number values for all samples. The returned copy number values are in units (copy number - 2) so that no amplification or deletion is 0, genes with amplifications have positive values, and genes with deletions are negative values. The data are converted from marker level to gene level using the extreme method: a gene is assigned the greatest amplification or the least deletion value among the markers it covers. Results may be filtered by cohort, gene, and/or barcode, but at least one gene or barcode must be supplied.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "gene": {
      "type": "array",
      "description": "Comma separated list of gene name(s)."
    },
    "tcga_participant_barcode": {
      "type": "array",
      "description": "Comma separated list of TCGA participant barcodes (e.g. TCGA-GF-A4EO)."
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "tcga_participant_barcode",
        "cohort",
        "gene"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Thresholded
This service provides access to the Gistic2 all_thresholded_by_genes.txt output data. A gene-level table of discrete amplification and deletion indicators for all samples. A table value of 0 means no amplification or deletion above the threshold. Amplifications are positive numbers: 1 means amplification above the amplification threshold; 2 means amplifications larger to the arm level amplifications observed for the sample. Deletions are represented by negative table values: -1 represents deletion beyond the threshold; -2 means deletions greater than the minimum arm-level deletion observed for the sample. Results maybe filtered by cohort, gene or barcode, but at least one gene or barcode must be supplied.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "gene": {
      "type": "array",
      "description": "Comma separated list of gene name(s)."
    },
    "tcga_participant_barcode": {
      "type": "array",
      "description": "Comma separated list of TCGA participant barcodes (e.g. TCGA-GF-A4EO)."
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "tcga_participant_barcode",
        "cohort",
        "gene"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: FeatureTable
This service returns part or all of the so-called <strong>feature table</strong>; which aggregates the most important findings across ALL pipelines in the GDAC Firehose analysis workflow into a single table for simple access.  One feature table is created per disease cohort.  Results may be filtered by date or cohort, but at least 1 cohort must be specified here. For more details please visit the <a href=https://confluence.broadinstitute.org/display/GDAC/Documentation\#Documentation-FeatureTable>online documentation</a>.  Please note that the service is still undergoing experimental evaluation and does not return JSON format.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "tsv",
        "csv"
      ]
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "date": {
      "type": "array",
      "description": "Select one or more date stamps."
    },
    "column": {
      "type": "array",
      "description": "Comma separated list of which data columns/fields to return."
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: MAF
This service returns columns from the MAF generated by MutSig. Results may be filtered by gene, cohort, tool, or barcode, but at least one gene OR barcode OR cohort must be given.  By default a subset consisting of the most commonly used columns will be returned, but that can be modified with the column parameter. Specifying 'all' in this parameter is a convenient way to return every column of the respective MAF, and has precedence over any any other column selection expression.  The complete list of column names that may be specified is <a href='http://firebrowse.org/api-docs/#!/Metadata/MAFColNames'>given here</a>.  For more information on the mutation data, and how it is processed by Firehose, please consult the <a href="https://confluence.broadinstitute.org/display/GDAC/Documentation#Documentation-MutationPipelines">pipeline documentation</a>.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "tool": {
      "type": "array",
      "description": "Narrow search to include only data/results produced by the selected Firehose tool."
    },
    "gene": {
      "type": "array",
      "description": "Comma separated list of gene name(s)."
    },
    "tcga_participant_barcode": {
      "type": "array",
      "description": "Comma separated list of TCGA participant barcodes (e.g. TCGA-GF-A4EO)."
    },
    "column": {
      "type": "array",
      "description": "Comma separated list of which data columns/fields to return."
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "tcga_participant_barcode",
        "cohort",
        "tool",
        "gene"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: SMG
This service provides a list of significantly mutated genes, as scored by MutSig.  It may be filtered by cohort, rank, gene, tool and/or Q-value threshold, but at least one cohort or gene must be supplied.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "tool": {
      "type": "array",
      "description": "Narrow search to include only data/results produced by the selected Firehose tool."
    },
    "rank": {
      "type": "integer",
      "format": "int32",
      "description": "Number of significant genes to return."
    },
    "gene": {
      "type": "array",
      "description": "Comma separated list of gene name(s)."
    },
    "q": {
      "type": "number",
      "description": "Only return results with Q-value <= given threshold.",
      "maximum": 1
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "q",
        "cohort",
        "tool",
        "gene",
        "rank"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Reports
This service returns URLs to the analysis result reports for runs of the Broad Institute GDAC Firehose analysis pipeline. At least one year of run reports are maintained in the database, but the reports from the latest run will be returned by default. The set of <a href="https://confluence.broadinstitute.org/display/GDAC/Nozzle">Nozzle</a> reports returned may be filtered by disease cohort, report type and report name.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "date": {
      "type": "array",
      "description": "Select one or more date stamps."
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "name": {
      "type": "array",
      "description": "Narrow search to one or more report names."
    },
    "type": {
      "type": "array",
      "description": "Narrow search to one or more report types."
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "date",
        "cohort",
        "type",
        "name"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Analyses.mRNASeq.Quartiles.get
For a given gene compute quartiles and extrema, suitable e.g. for drawing a boxplot (Tukey 1977).  Results may be filtered by cohort, sample type, patient barcode  or characterization protocol, and are returned sorted by cohort.  Note that samples for which no expression value was recorded (e.g. <a href="http://firebrowse.org/api/v1/Samples/mRNASeq?&gene=egfr&cohort=SKCM&tcga_participant_barcode=TCGA-GN-A262">the melanoma sample TCGA-GN-262</a>) are removed prior to calculation.

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "gene": {
      "type": "string",
      "description": "Enter a single gene name."
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "protocol": {
      "type": "array",
      "description": "Narrow search to one or more sample characterization protocols from the scrollable list."
    },
    "sample_type": {
      "type": "array",
      "description": "For which type of sample(s) should quartiles be computed?"
    },
    "Exclude": {
      "type": "array",
      "description": "Comma separated list of TCGA participants, identified by barcodes such as TCGA-GF-A4EO, denoting samples to exclude from computation."
    }
  },
  "additionalProperties": false,
  "required": [
    "gene"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: StandardData
This service returns the archive URLs for our Firehose standard data runs, providing a RESTful interface similar in spirit to the command line <a href="https://confluence.broadinstitute.org/display/GDAC/Download">firehose_get</a> tool. The archives can be filtered based on date, cohort, data type, platform, center, data level, and protocol.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "date": {
      "type": "array",
      "description": "Select one or more date stamps."
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "data_type": {
      "type": "array",
      "description": "Narrow search to one or more TCGA data types from the scrollable list."
    },
    "tool": {
      "type": "array",
      "description": "Narrow search to include only data/results produced by the selected Firehose tool."
    },
    "platform": {
      "type": "array",
      "description": "Narrow search to one or more TCGA data generation platforms from the scrollable list."
    },
    "center": {
      "type": "array",
      "description": "Narrow search to one or more TCGA centers from the scrollable list."
    },
    "level": {
      "type": "array",
      "description": "Narrow search to one or more TCGA data levels."
    },
    "protocol": {
      "type": "array",
      "description": "Narrow search to one or more sample characterization protocols from the scrollable list."
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "cohort",
        "protocol",
        "center",
        "data_type",
        "level",
        "tool",
        "platform",
        "date"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Centers
By default this function returns a table of all consortium members in TCGA, aka centers; it provides both the HTTP domain and full organizational name of each center.  A subset of this table may be obtained by explicitly specifying one or more domain names.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "center": {
      "type": "array",
      "description": "Narrow search to one or more TCGA centers from the scrollable list."
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: ClinicalNames
Retrieve names of all patient-level clinical data elements (CDES) available in TCGA, unioned across all disease cohorts. A CDE will be listed here only when it has a value other than NA for at least 1 patient case in any disease cohort. For more information on how these CDEs are processed see our <a href="https://confluence.broadinstitute.org/display/GDAC/Documentation">pipeline documentation</a>.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: ClinicalNames_FH
This service returns the names of patient-level clinical data elements (CDEs) that have been normalized by Firehose for use in analyses, unioned across all disease cohorts. For more information on how these CDEs are processed, see our <a href="https://confluence.broadinstitute.org/display/GDAC/Documentation">pipeline documentation</a>.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Cohorts
By default this function returns a table containing all TCGA cohort abbreviations and their corresponding disease names.  A subset of that table may be obtained by explicitly specifying one or more cohort abbreviations.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Counts
Returns the aliquot counts for each disease cohort, per sample
type and data type.  The sample type designation of "Tumor"
may be used to aggregate the count of all tumor aliquots into
a single number per disease and data type. See the SampleTypes
function for a complete description of sample types.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "date": {
      "type": "array",
      "description": "Select one or more date stamps."
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "sample_type": {
      "type": "array",
      "description": "Narrow search to one or more TCGA sample types from the scrollable list."
    },
    "data_type": {
      "type": "array",
      "description": "Narrow search to one or more TCGA data types from the scrollable list."
    },
    "totals": {
      "type": "boolean",
      "description": "Output an entry providing the totals for each data type."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "cohort"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Dates
Retrieve datestamps of all GDAC Firehose standard data and analyses runs that have been ingested into FireBrowse.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: HeartBeat
Returns a message to indicate that API (server) is up and running, or times out if not.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: MAFColNames
Retrieve the names of all columns in the mutation annotation files (MAFs) hosted by FireBrowse.  For more information on the mutation data, and how it is processed by Firehose, please consult the <a href="https://confluence.broadinstitute.org/display/GDAC/Documentation#Documentation-MutationPipelines">pipeline documentation</a>.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Patients
This service returns a list of all TCGA patient barcodes in FireBrowse, optionally filtered by disease cohort.  The barcodes are obtained directy from the clinical data.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "cohort"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Platforms
By default this function returns a table of all of the technology platforms used to sequence or characterize samples in TCGA--both their short platform codes and full names.  A subset of this table may be obtained by explicitly specifying one or more platform codes.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "platform": {
      "type": "array",
      "description": "Narrow search to one or more TCGA data generation platforms from the scrollable list."
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Barcode
Given a TCGA barcode, return its short letter sample type code.

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "TCGA_Barcode": {
      "type": "string",
      "description": "Enter a single TCGA barcode, of any form: e.g. TCGA-GF-A4EO-06 or TCGA-EL-A3D5-01A-22D-A202-08"
    }
  },
  "additionalProperties": false,
  "required": [
    "TCGA_Barcode"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: Code
Convert a TCGA numeric sample type code (e.g. 01, 02) to its corresponding symbolic (short letter) code (e.g. TP, TR).

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "code": {
      "type": "array",
      "description": "Narrow search to one or more TCGA sample type codes."
    }
  },
  "additionalProperties": false,
  "required": [
    "code"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: ShortLetterCode
Convert a TCGA sample type code in symbolic form (or 'short letter code' like TP, TR) to its corresponding numeric form (e.g. 01, 02).

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "short_letter_code": {
      "type": "array",
      "description": "TCGA sample type short letter code(s) (e.g. TP, NB, etc.). "
    }
  },
  "additionalProperties": false,
  "required": [
    "short_letter_code"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: SampleTypes
Return all TCGA sample type codes, both numeric and symbolic.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: TSSites
By default this function returns a table of all sites which contributed source tissue to TCGA, aka TSS's. A subset of this table may be obtained by explicitly specifying one or more sites.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "tss_code": {
      "type": "array",
      "description": "Narrow search to one or more TSS codes"
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Clinical
This service returns patient clinical data from TCGA, verbatim. It differs from the Samples/Clinical_FH method by providing access to all TCGA CDEs in their original form, not merely the subset of CDEs normalized by Firehose for analyses.  Results may be selected by disease cohort, patient barcode or CDE name, but at least one cohort, barcode, or CDE must be provided. When filtering by CDE note that only when a patient record contains one or more of the selected CDEs will it be returned. Visit the Metadata/ClinicalNames api function to see the entire list of TCGA CDEs that may be queried via this method. For more information on how clinical data are processed, see our <a href="https://confluence.broadinstitute.org/display/GDAC/Documentation#Documentation-ClinicalPipeline">pipeline documentation</a>.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "tcga_participant_barcode": {
      "type": "array",
      "description": "Comma separated list of TCGA participant barcodes (e.g. TCGA-GF-A4EO)."
    },
    "cde_name": {
      "type": "array",
      "description": "Retrieve results only for specified CDEs, per the Metadata/ClinicalNames function"
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "tcga_participant_barcode",
        "cohort",
        "cde_name"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: Clinical_FH
This service returns patient-level clinical data elements (CDEs) that have been normalized by Firehose for use in analyses. Results may be selected by disease cohort, patient barcode or CDE name, but at least one cohort, barcode or CDE must be provided. When filtering by CDE note that only when a  patient record contains one or more of the selected CDEs will it be returned. Visit <a href="http://gdac.broadinstitute.org/runs/info/clinical">this table of CDEs</a> to see what's available for every disase cohort; for more information on how these CDEs are processed see our <a href="https://confluence.broadinstitute.org/display/GDAC/Documentation#Documentation-ClinicalPipeline">pipeline documentation</a>.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "tcga_participant_barcode": {
      "type": "array",
      "description": "Comma separated list of TCGA participant barcodes (e.g. TCGA-GF-A4EO)."
    },
    "fh_cde_name": {
      "type": "array",
      "description": "Retrieve results only for the CDEs specified from the scrollable list."
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "tcga_participant_barcode",
        "cohort",
        "fh_cde_name"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: mRNASeq
This service returns sample-level log2 mRNASeq expression values. Results may be filtered by gene, cohort, barcode, sample type or characterization protocol, but at least one gene must be supplied.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "gene": {
      "type": "array",
      "description": "Comma separated list of gene name(s)."
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "tcga_participant_barcode": {
      "type": "array",
      "description": "Comma separated list of TCGA participant barcodes (e.g. TCGA-GF-A4EO)."
    },
    "sample_type": {
      "type": "array",
      "description": "Narrow search to one or more TCGA sample types from the scrollable list."
    },
    "protocol": {
      "type": "array",
      "description": "Narrow search to one or more sample characterization protocols from the scrollable list."
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "tcga_participant_barcode",
        "cohort",
        "gene",
        "protocol",
        "sample_type"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```
## Operation: miRSeq
This service returns sample-level log2 miRSeq expression values. Results may be filtered by miR, cohort, barcode, sample type or Firehose preprocessing tool, but at least one miR must be supplied.

### Input Schema
```json
{
  "type": [
    "object",
    "null"
  ],
  "properties": {
    "format": {
      "type": "string",
      "description": "Format of result.",
      "enum": [
        "json",
        "tsv",
        "csv"
      ]
    },
    "mir": {
      "type": "array",
      "description": "Comma separated list of miR names (e.g. hsa-let-7b-5p,hsa-let-7a-1)."
    },
    "cohort": {
      "type": "array",
      "description": "Narrow search to one or more TCGA disease cohorts from the scrollable list."
    },
    "tcga_participant_barcode": {
      "type": "array",
      "description": "Comma separated list of TCGA participant barcodes (e.g. TCGA-GF-A4EO)."
    },
    "tool": {
      "type": "array",
      "description": "Narrow search to include only data/results produced by the selected Firehose tool."
    },
    "sample_type": {
      "type": "array",
      "description": "Narrow search to one or more TCGA sample types from the scrollable list."
    },
    "page": {
      "type": "array",
      "description": "Which page (slice) of entire results set should be returned. "
    },
    "page_size": {
      "type": "array",
      "description": "Number of records per page of results.  Max is 2000."
    },
    "sort_by": {
      "type": "string",
      "description": "Which column in the results should be used for sorting paginated results?",
      "enum": [
        "tcga_participant_barcode",
        "cohort",
        "tool",
        "mir",
        "sample_type"
      ]
    }
  },
  "additionalProperties": false
}
```
### Output Schema
```json
{}
```