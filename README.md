# MYE References 

Collection of information that was found by trial and error or by searching for answers online.  


## To run 

Build > Render Book 

**Manually** copy over pdf files from `img` to `docs/img` 

```
df <- data.frame(
  v1 = list.files(path = file.path(getwd(), "img"), pattern = "pdf$", full.names = TRUE), 
  v2 = paste0(file.path(getwd(), "docs/img"), list.files(path = "img", pattern = ".pdf$"))
)
mapply(file.copy, from = df$v1, MoreArgs = list(to = df$v2, overwrite = TRUE))
```