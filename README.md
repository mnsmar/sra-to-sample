`sra-to-sample` downloads SRA files and creates the corresponding sample
directory structure. The input to the script is a JSON file.

e.g. The following JSON file

```json
{ "samples":[
    {"id": "sample_id_1", "name": "sample_name_1", "sra": ["SRRXXXXX", "SRRXXXXX"]},
    {"id": "sample_id_2", "name": "sample_name_2", "sra": ["SRRXXXXX"]}
]}
```

results in the following directory structure

```
sample_name_1
  |-fastq/reads.1.fastq.gz
  |-fastq/reads.2.fastq.gz
  README
sample_name_2
  |-fastq/reads.1.fastq.gz
  |-fastq/reads.2.fastq.gz
  README
```

Note that when multiple SRA codes are associated with a sample, as in the
first line of the example JSON, the files are concatenated in one fastq file.
