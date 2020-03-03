# Web-Scrapping-Project -

GEO is an international public repository that archives and freely distributes microarray, next-generation sequencing, and other forms of high-throughput functional genomics data submitted by the research community. It stores these datasets in a database. For each GEO ID, it has information like Title, summary, organisms, experiment type, overall design and citations.

#### GSE IDs:  GSE63312, GSE78224, GSE74018, GSE50734, GSE114644, GSE60477, GSE53599, GSE80582, GSE109493, GSE35200

## First part of project is to - 
### Write a script to scrap all the relevant information from the GEO website for above GSE IDs and store it into a Database (postgres).

Once we prepared database, we want to know about the nature of each data sets. One of the approaches may be to look at the biological keywords within the summary. In order to get the keyword, we can annotate the summary of data sets by Becas APIs . This allows you to programmatically annotate text or PubMed abstracts with biomedical concepts on the fly. The becas API annotates text and PubMed abstracts with biomedical concepts. Each keyword belongs to a given semantic group or entity type (like diseases, anatomy, proteins etc). You are required to annotate the summary of each dataset if they are present. Becas APIs Returns a JSON object.

The output(json obj) contains the entities (biological keywords), which is are our main concern. It’s encoded as | separated 3 element tuples. 1st element is basically the keyword (entity), 2nd is a unique identifier for that keyword and you can ignore the third element
for this project. 
Every keyword has a unique identifier , a string like NCBI:9606:T001: SPEC . This unique identifier is made up of four parts separated by colons. The first part identifies the data source where the concept is registered; the second part is the concept identifier in that data source; the third part is the sub-group of the concept, and the last part is the concept type.

## Second part of the project is to - 
### Store the annotated keywords of each dataset within the Database and write a query to get all the dataset IDs which contains disease keyword.
