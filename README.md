# manu_update_humandb
update a database for annotation platforms based on ANNOVAR (such as varAFT) 

## *Step1 download database*

1. check database files in the website.
   https://annovar.openbioinformatics.org/en/latest/user-guide/download/
   
   <img width="860" alt="image" src="https://user-images.githubusercontent.com/22020125/223757336-2cef54a4-784b-4e06-95a2-85e7cc22d028.png">

2. create the download link by following the naming system (example: hg19_clinvar20221231)
   
   **Linux**
   >> wget http://www.openbioinformatics.org/annovar/download/hg19_clinvar_20221231.txt.gz
   
   >> wget http://www.openbioinformatics.org/annovar/download/hg19_clinvar_20221231.txt.idx.gz
   
   **Windows**
   
   double click 
   
   http://www.openbioinformatics.org/annovar/download/hg19_clinvar_20221231.txt.gz
   
   http://www.openbioinformatics.org/annovar/download/hg19_clinvar_20221231.txt.idx.gz
   
   **ANNOVAR commend line**
   -  check the database list
   
      >> perl annotate_variation.pl --downdb avdblist --webfrom annovar --buildver hg19 .
      
      ![image](https://user-images.githubusercontent.com/22020125/223760457-5cfb099f-3692-47bc-8165-d7b0d33892a8.png)
   -  download the database
      
      >> perl annotate_variation.pl --downdb hg19_clinvar_20221231 D:\humandb/hg19/ -webfrom annovar -buildver hg19
      
      ![image](https://user-images.githubusercontent.com/22020125/223760708-4eae0645-8a26-434f-b6e1-70ee09a8a952.png)

## *Step2 create an index file for database when data wasn't coming with an index file*
1. if no idx, create a idx file for customized database in Linux
   >> perl index_annovar.pl xxx.txt.gz

## *Step3 move files to the database folder*
1. move txt and idx files into the databse folder ( *D:\humandb/* )
2. modify the name for the naming systme of softwares such as varAFT.
   
   Rename "hg19_clinvar_20221231" to "hg19_clinvar"
3. you are ready to go.

