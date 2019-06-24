# convert GRch37 to hg19  
     
ftp://gsapubftp-anonymous@ftp.broadinstitute.org/Liftover_Chain_Files/b37tohg19.chain
     
     gatk  --java-options "-Djava.io.tmpdir=./ -Xmx60G"" LiftoverVcf -I query.vcf.gz -O query.hg19.vcf.gz -R ucsc.hg19.fasta --REJECT unmapped.vcf -C b37tohg19.chain
     
     bgzip -c query.hg19.vcf > query.hg19.vcf.gz
     
     tabix -p vcf query.hg19.vcf.gz
     
 http://hgdownload.cse.ucsc.edu/gbdb/hg19/liftOver/
 
 http://bioinfo5pilm46.mit.edu/software/GATK/resources/    
