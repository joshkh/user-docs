FASTA
================================


Types of data loaded
--------------------

features and their sequences. Will create a feature for each entry in a fasta file and set the sequence, the class of the feature to create is set for the whole file.

How to download the data 
---------------------------

N/A - will parse any file in FASTA format

How to load the data into your mine
--------------------------------------

project XML example

.. code-block:: xml

    <source name="flybase-dmel-gene-fasta" type="fasta">
      <property name="fasta.taxonId" value="7227"/>
      <property name="fasta.dataSetTitle" value="FlyBase fasta data set for Drosophila melanogaster"/>
      <property name="fasta.dataSourceName" value="FlyBase"/>
      <property name="fasta.className" value="org.intermine.model.bio.Gene"/>
      <property name="fasta.classAttribute" value="primaryIdentifier"/>
      <property name="fasta.includes" value="dmel-all-gene-*.fasta"/>
      <property name="src.data.dir" location="/DATA/flybase/fasta/current"/>
    </source>


===============  ===================================================  =========================================================
attribute        content                                              purpose 
===============  ===================================================  =========================================================
taxonId          space-delimited list of taxonIds                     only features with the listed taxonIds will be loaded 
className        fully-qualified class name                           determines which feature will be loaded 
classAttribute   identifier field from className                      determines which field from the feature will be set 
dataSetTitle     name of dataset                                      determines name of dataset object 
dataSourceName   name of datasource                                   determines name of datasource object  
src.data.dir     location of the fasta data file                      these data will be loaded into the database 
includes         name of data file                                    this data file will be loaded into the database 
sequenceType     class name                                           type of sequence to be loaded 
loaderClassName  name of Java file that will process the fasta files  only use if you have created a custom fasta loader 
===============  ===================================================  =========================================================

.. index:: FASTA, sequences
