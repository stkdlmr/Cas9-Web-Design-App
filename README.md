# Cas9-Web-Design-App
Building a web application to streamline the design of gRNAs for Cas9 genome editing.

## JBrowse
We are using JBrowse to visualize the genome sequence and various annotations such as genes and protein-coding transcripts.

### 1. Set up Reference Genome:
Download the reference sequence (ex. mm10.fa). Navigate to ```/var/www/jbrowse/``` and run:
```bash
$ bin/prepare-refseqs.pl --fasta genome/mm10.fa
```
### 2. Prepare information for specific tracks:
Again, in ```/var/www/jbrowse/```, run ```bin/flatfile-to-json.pl``` to generate track-specific json. For example, to set up a Gene track to show genes:
```
$ bin/flatfile-to-json.pl --tracklabel gene --key “Gene” --gff docs/tutorial/data_files/volvox.gff3 --cssclass feature2 --getLabel --type gene --autocomplete all
```
```--autocomplete all``` allows genes to be searched for by name in the search bar. 

For more details on parameter settings, see the [JBrowse paper at NCBI](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4350995/).
#### To enable searching by name, run:
```
$ bin/generate-names.pl
```
#### Finally, to view updated information in the browser, navigate to the [site](https://crispor.ccm.sickkids.ca/jbrowse/index.html)
