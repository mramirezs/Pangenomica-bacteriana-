# Pangenomica-bacteriana

## Obtención de archivos gb del NCBI

* Leptospira interrogans **serovar** Bataviae strain 1489 chromosome 1, complete sequence

```
efetch -db nuccore -id NZ_CP043893.1 -format gb -style master > NZ_CP043893.1.gb
```

* Leptospira interrogans **serovar** Canicola strain 782 chromosome 1, complete sequence

```
efetch -db nuccore -id NZ_CP043884.1 -format gb -style master > NZ_CP043884.1.gb
```

* Leptospira interrogans **serovar** Copenhageni strain FDAARGOS_203 chromosome, complete genome

```
efetch -db nuccore -id NZ_CP020414.2 -format gb -style master > NZ_CP020414.2.gb
```

* Leptospira interrogans **serovar** Icterohaemorrhagiae strain Langkawi chromosome 1, complete sequence

```
efetch -db nuccore -id NZ_CP043876.1 -format gb -style master > NZ_CP043876.1.gb
```

* Leptospira interrogans **serovar** Lai str. 56601 chromosome I, complete sequence

```
efetch -db nuccore -id NC_004342.2 -format gb -style master > NC_004342.2.gb
```

* Leptospira interrogans **serovar** Linhai str. 56609 chromosome 1, complete sequence

```
efetch -db nuccore -id NZ_CP006723.1  -format gb -style master > NZ_CP006723.1.gb
```

## Convertir archivos gb a gff 

```
bp_genbank2gff -stdout -file NZ_CP043893.1.gb > NZ_CP043893.1.gff
```

Tambien podríamos ejecutar:

```
bp_genbank2gff -stdout -accession NZ_CP043893.1 > NZ_CP043893.1.gff
```

## Visualización de resultados

Primero, necesitamos generar un archivo newick a partir de la alineación generada por Roary:

```
FastTree -nt -gtr core_gene_alignment.aln > my_tree.newick
```

Luego, podemos hacer el plot de los resultados con el script roary_plots.py:

```
roary_plots.py my_tree.newick gene_presence_absence.csv
```

