# stacks genotyping

First, download stacks from [this link](https://catchenlab.life.illinois.edu/stacks/)

Then, install the program following these steps, within the comand line : 

```bash
tar xfvz stacks-exact-version-here.tar.gz
cd stacks-folder
./configure
make

make install #if that fails, do sudo make install
```

### Running the denovo_map pipeline

> Today, we are going to try to genotype, from scratch (aka denovo) our genomics data that we had been working with earlier in the semester. 
> 

The `denovo_map.pl` pipeline in essense runs the four most important steps/programs of the genotyping pipeline, and is thus of major importance to troubleshoot parameters and think about all available options as shown in the [manual](https://catchenlab.life.illinois.edu/stacks/comp/denovo_map.php)

>------------
>
> Before running the pipeline, we need to generate a [population map](https://catchenlab.life.illinois.edu/stacks/manual/#popmap) file, or a `popmap.txt` file. This file is only made up of two columns separated by tab. The first column contains the sample/file name, and the second one contains the population ID. The sample ID is contained within the names of the files, such that in the file `Bjimenezi_Churi1.fq`, the population is `Churi`. Generate a file (shared as a class if you want!) named `popmap.txt` that is formatted as explained above (and below). The file has no header. 

	Bjimenezi_Churi1		Churi

> 
> ----------------



> **IMPORTANT:** Make sure that all your fastq (sequence data) files are within a folder named `raw-data` and that all the files are gzipped (ending in `fq.gz`). ***You must have both the raw data folder and the `popmap.txt` file within the directory you are running the code from, for the code below to work.***
> 
> -------------

Once everything above is finalized, we are ready to run the code for our `denovo_map.pl` pipeline for our six samples. 

```bash
mkdir denovo
denovo_map.pl -T 2 -m 3 -M 2 -n 2 -o ./denovo --samples ./raw-data --popmap popmap.txt
```

OK, let's execute **`denovo_map.pl`**!!! Look at the terminal window as it runs.... what's happening currently...? 

While we wait, let's talk about the components of the `denovo_map.pl` pipeline in this [mini-lecture](https://docs.google.com/presentation/d/e/2PACX-1vSWd71ghS8mMujg7bqpAU_4PhPBqv8KUSYPwfgFI2BqAdBte8xA1zCxbiFFp194Tw/pub?start=false&loop=false&delayms=60000), and try to understand what is currently going on. 


