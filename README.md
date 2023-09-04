# HiDENSEC: Code for Tracing cancer evolution and heterogeneity using Hi-C

Given a .hic file, in order to prepare it for running HiDENSEC, run the following command: 
```
java -jar juicer_tools.jar dump observed NONE <INPUT.hic> assembly assembly BP 25000 | tail -n+2 | awk -F $"\t" '{print $1*2"\t"$2*2"\t"$3}' | awk -F $"\t" '{print (($1/50000)+1)"\t"(($2/50000)+1)"\t"$3}' > <OUTPUT.hi-c_matrix>
```

Here, `INPUT.hic` is the Hi-C file which can be generated using `https://github.com/aidenlab/juicer`. 
The `OUTPUT.hi-c_matrix` is the output file name which will then be fed into the HiDENSEC jupyter notebook.
The `juicer_tools.jar` can be downloaded from `https://github.com/aidenlab/juicer/wiki/Download`
