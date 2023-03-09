# manu_update_humandb
Update a database for annotation platforms based on ANNOVAR (such as varAFT) 

## *Step1 Download database*

1. Check database files in the website.
   https://annovar.openbioinformatics.org/en/latest/user-guide/download/
   
   > ![image](https://user-images.githubusercontent.com/22020125/223897405-bbf4e4b1-4d57-4927-a11b-a0e9e28250d7.png)

2. Create the download link by following the naming system (example: hg19_clinvar20220320)
   
   ### **Linux**
   
   Code
   
    ` wget http://www.openbioinformatics.org/annovar/download/hg19_clinvar_20220320.txt.gz`
   
    ` wget http://www.openbioinformatics.org/annovar/download/hg19_clinvar_20220320.txt.idx.gz`
   
   ### **Windows**
   
    Double click 
   
    > http://www.openbioinformatics.org/annovar/download/hg19_clinvar_20220320.txt.gz
   
    > http://www.openbioinformatics.org/annovar/download/hg19_clinvar_20220320.txt.idx.gz
   
   ### **ANNOVAR commend line**
    Check the database list
   
    `perl annotate_variation.pl --downdb avdblist --webfrom annovar --buildver hg19 .`
      
    > ![image](https://user-images.githubusercontent.com/22020125/223760457-5cfb099f-3692-47bc-8165-d7b0d33892a8.png)
    
    Download the database
      
    `perl annotate_variation.pl --downdb hg19_clinvar_20220320 D:\humandb/hg19/ -webfrom annovar -buildver hg19`
      
    > ![image](https://user-images.githubusercontent.com/22020125/223760708-4eae0645-8a26-434f-b6e1-70ee09a8a952.png)

## *Step2 Create an index file for database when data wasn't coming with an index file*
1. if no idx, create a idx file for customized database in Linux
   
   ` perl index_annovar.pl xxx.txt.gz`

## *Step3 Move files to the database folder*
1. Move txt and idx files into the databse folder ( *D:\humandb/* )
2. Modify the name for the naming systme of softwares such as varAFT.
   > Rename "hg19_clinvar_20220320" to "hg19_clinvar"

## *Step4 You are ready to go!*

