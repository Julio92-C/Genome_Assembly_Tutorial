# Genome_Assembly_Tutorial
Assembly of small and mid-sized genomes using ONT dataset

# Command use in this tutorials

1- flye (assembler)

>>> flye --nano-raw ecoli.30x.r103.fastq.gz --out-dir ./flye_output/flye --genome-size 5m --threads 8

2- medaka (polisher)

>>> medaka_consensus -i ecoli.30x.r103.fastq.gz -d ./flye_output/flye/assembly.fasta -o medaka -t 8 -m r103_min_high_g345

3- pomoxis (quality analysis)

>>> assess_assembly -r references.fasta -i ./medaka/consensus.fasta -p ./assessment/assm -t 8

4- agb (Assembly Graph Browser)

>>> agb.py -i ./flye_output/flye -a flye -r references.fasta -o agb_output
