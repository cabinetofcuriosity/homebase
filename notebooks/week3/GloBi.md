
## Author: Yikang Li

## GloBi:

Global Biotic Interactions (GloBI) provides open access to species interaction data (e.g., predator-prey, pollinator-plant, pathogen-host, parasite-host) by combining existing open datasets using open source software. By providing an infrastructure to capture and share interaction data, individual biologists can focus on gathering new interaction data and analyzing existing datasets without having to spend resources on (re-) building a cyberinfrastructure to do so.

GloBI is made possible by a community of software engineers, bioinformaticists and biologists. Software engineers such as Jorrit Poelen, Göran Bodenschatz, and Robert Reiz collaborate with bioinformaticists like Chris Mungall, data managers like Sarah E. Miller and biologists like Jim Simons, Anne Thessen, Jen Hammock and Brian Hayden to capture, provide access to and use interaction data that is provided by biologists and citizen scientists around the world. GloBI is funded by EOL's Rubenstein Fellowship Program.

### Access GloBi:

There is a package called "rglobi" in R which allows us to access the database on Global Biotic Interactions (GloBI).  
  
Description from the documentation of package:  
"A programmatic interface to the web service methods provided by Global Biotic Interactions (GloBI). GloBI provides access to spatial-temporal species interaction records from sources all over the world. rglobi provides methods to search species interactions by location, interaction type, and taxonomic name. In addition, it supports Cypher, a graph query language, to allow for executing custom queries on the GloBI aggregate species interaction data set."  

First, we need to install and library the package "rglobi" in R.

```{}
install.packages("rglobi")
library(rglobi)
```
There are many methods available in "rglobi" for users to extract data. Users are able to search data on species interactions by location, interaction type, and taxonomic name.  

Here is a list of all functions in the package. While the usages are kind of intuitive, you can find detailed documentations [here:](https://rdrr.io/cran/rglobi/man/)  

```{}
get_child_taxa : function (taxon.names, rank = "Species", skip = 0, limit = 25, opts = list())    
get_data_fields : function (opts = list())    
get_interaction_areas : function (bbox = NULL, ...)    
get_interaction_matrix : function (source.taxon.names = list("Homo sapiens"), target.taxon.names = list("Mammalia"), interaction.type = "eats", 
    opts = list())    
get_interaction_table : function (source.taxon.names = list(), target.taxon.names = list(), interaction.type = "preysOn", skip = 0, 
    limit = 100, opts = list())    
get_interaction_types : function (opts = list())    
get_interactions : function (taxon = "Homo sapiens", interaction.type = "preysOn", ...)    
get_interactions_by_taxa : function (sourcetaxon, targettaxon = NULL, interactiontype = NULL, accordingto = NULL, showfield = c("source_taxon_external_id", 
    "source_taxon_name", "source_taxon_path", "source_specimen_life_stage", "interaction_type", "target_taxon_external_id", 
    "target_taxon_name", "target_taxon_path", "target_specimen_life_stage", "latitude", "longitude", "study_citation", 
    "study_external_id", "study_source_citation"), otherkeys = NULL, bbox = NULL, returnobservations = F, opts = list())    
get_interactions_by_type : function (interactiontype = c("interactsWith"), ...)    
get_interactions_in_area : function (bbox, ...)    
get_predators_of : function (taxon = "Rattus rattus", ...)    
get_prey_of : function (taxon = "Homo sapiens", ...)    
query : function (cypherQuery, opts = list())   
```

For example,  if we want to get species interactions by interaction type from GloBI, we could use:   
```{}
get_interactions_by_type(interactiontype = c("interactsWith"), ...)
```
We can input any interactiontype to get all data with that interactiontype.   

Also, we can build an table of taxon A's interaction type B. The output of get_interactions has columns for the source and target taxa species:    
```{}
get_interactions(taxon = "Homo sapiens", interaction.type = "preysOn", ...)
```
All other functions perform in similar ways. Examples can be found in the documentation.  

### Getting the dataframe for all interactions with interaction type "preysOn":  
Let's say we are interested in interaction type "preysOn" and therefore want to extract all data records involving that. We simply do:  
```{}
df = get_interactions_by_type(interactiontype = c("preysOn"))
write.csv(df, "GloBi_PreysOn.csv", row.names = FALSE)
```
Now we should have a csv file "GloBi_preysOn.csv" locally and we can read and use it afterwards.

### Reference:
Jorrit H. Poelen, James D. Simons and Chris J. Mungall. (2014). Global Biotic Interactions: An open infrastructure to share and analyze species-interaction datasets. Ecological Informatics. https://doi.org/10.1016/j.ecoinf.2014.08.005.


