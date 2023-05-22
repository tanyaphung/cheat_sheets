## scanpy

[https://scanpy.readthedocs.io/en/stable/generated/scanpy.get.obs_df.html#scanpy.get.obs_df](https://scanpy.readthedocs.io/en/stable/generated/scanpy.get.obs_df.html#scanpy.get.obs_df)

- Load a scanpy object:

```
adata = sc.read_h5ad('anndata.h5ad')
#or:
adata = anndata.read("anndata.h5ad")
```

- Subset the adata object for a list of cells
```
col_ids = ["AAACCCACACTCCTGT_TSP6_Liver_NA_10X_1_1", "AAACGAAGTACCAGAG_TSP6_Liver_NA_10X_1_1"] 
test_subset = sc.get.var_df(adata, keys=col_ids)
```

- Get gene names if the gene names are the index of adata.var
```
adata.var_names
```

- Get cell names:
```
print(set(adata.obs_names))
```

- Number of cells:
```
adata.shape[0]
```

- Get metadata:
```
adata.obs
```

- Get raw data:
```
adata.raw.X
```

- View sparse matrix:
```
from scipy.sparse.csc import csc_matrix
adata.X.A
#or:
adata.raw.X.A
```

- Loading large dataset:
  + large datasets in h5ad format can be more easily handled if we read them using and additional ” backed= ‘r’ ” to the anndata.read function. 
  + We then can make subsets of cells (genes) with only the .var and .obs in memory, and keep the data itself stored on disk
  + reference: https://scanpy.readthedocs.io/en/latest/generated/scanpy.read_h5ad.html#scanpy-read-h5ad
