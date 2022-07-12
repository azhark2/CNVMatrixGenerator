# CNVMatrixGenerator
Mutational Signatures for copy number alterations

## COPY NUMBER MATRIX GENERATION

In order to generate a copy number matrix, provide the an absolute path to a multi-sample segmentation file obtained from one of the following copy number calling tools listed below(if you have individual sample files, please combine them into one file with the first column corresponding to the sample name). Please note that your segmentation file should contain a "sample" column, the chromosome, start and end of a segment, and the copy number of the A and B allele.

1. ASCAT
2. ASCAT_NGS
3. SEQUENZA
4. ABSOLUTE
5. BATTENBERG
6. FACETS
7. PURPLE
8. ICGC-consensus
9. TCGA

In addition, provide the name of the project and the output directory for the resulting matrix.

An example to generate the CNV matrix is as follows:

$ python3
```
>>from CNVMatrixGenerator.scripts import CNVMatrixGenerator as scna
>>file_type = "BATTENBERG"
#example input file for testing
>>input_file = "./example_input/Battenberg_test.tsv"
>>output_path = "."
>>project = "Breast_Cancer"
>>scna.generateCNVMatrix(file_type, input_file, project, output_path)

```

Alternatively, you can run directly from the command line:
```
python ./CNVMatrixGenerator/scripts/CNVMatrixGenerator.py BATTENBERG ./example_input/Battenberg_test.tsv BATTENBERG-TEST ./example_output/

```
