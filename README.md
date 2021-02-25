# Peptide-Vaccine-Analysis-Tool-PVAT
<< Please read this entire document carefully before using the software >>

*** HOW TO USE PEPTIDE VACCINE ANALYSIS TOOL – PVAT ***

Select the required zip/rar file based on the OS (Windows/macOS) and architecture (32/64 bit) and navigate to the “dist” folder to open the PVAT software.

•	This software aims at studying a set of amino acid sequences of any target protein. All possible consecutive amino acid stretches of length 12 are considered from the sequences and then the conservativeness and surface accessibility of the all these stretches are studied. Finally a rank list is prepared by the software that ranks the peptides such that the top ranks are occupied by peptides having relatively higher conservativeness and higher surface accessibility. 

•	For more information on the above method of ranking the peptides, please go through the following links:
•	https://doi.org/10.1109/ICCECE48148.2020.9223075 
•	https://sciforum.net/paper/view/conference/6787 
•	https://www.researchgate.net/publication/344545959_Archives_of_Proteomics_and_Bioinformatics_Commentary_A_Bioinformatics_Protocol_for_Rational_Design_of_Peptide_Vaccines_and_the_COVID-19_Rampage 

•	The software has three mandatory fields for input:
1.	for entering the pathname of the file containing the input amino acid sequences
2.	for entering the pathname of the folder containing the files for surface accessibility values
3.	for entering the pathname of the folder where the user wants all the output files to be produced

•	For point 1 mentioned above, please visit to the official website of NCBI (https://www.ncbi.nlm.nih.gov/) and select the “Protein” tab to the left of text search field. Enter the required details in the search field and download the required sequences as: Send to > File > Format > FASTA. The path where the downloaded FASTA file is stored in the system is the required pathname for point 1.

•	For the point 2 mentioned above, a standard online protein structure prediction server named “SABLE” is to be used here (http://sable.cchmc.org/). Basically SABLE server gives a measure of surface exposure for each amino acid position in the sequence on a scale of 0-100. Hence, firstly, on the same NCBI search results page from where the sequences have been downloaded as FASTA, consider the reference sequence (RefSeq). Note down the accession ID and the number of constituent amino acids of the RefSeq (generally, RefSeq acc. Ids have an underscore in their name). Next, go to the downloaded FASTA file and follow the steps as: Edit > Find > Enter the search field as the accession ID of the RefSeq. Select the entire amino acid sequence under that accession ID of the RefSeq and paste it in the text box field in the SABLE server. Remove the line spaces from the text given and enter the email ID where the results will be given. Click on “Submit” and wait for some time after which the results will arrive in the entered email ID.

•	From the email sent from SABLE server, move to the section “Relative solvent accessibility prediction (real values)”. Select the text from “>  1” up to the accessibility value for the last amino acid position and paste the entire the text into a blank text file (Notepad in Windows or TextEdit in macOS). Store the text file into a blank folder and rename the text file as “1.txt”. Now using the same length as that of the RefSeq that was previously noted down, select two more sequences from the FASTA file, preferably from different communities. Enter their respective sequences and store their corresponding outputs as “2.txt” and “3.txt” respectively, inside the same folder. By doing the above process for point 2, it is now made sure that the position-wise changes in the surface accessibility values as a result in mutation across different communities are all covered. Please make sure that there is only one blank sentence with no space character at the end of each of the 3 text files. 

•	For point 3, create a blank folder, where the outputs will be stored.

•	 Now,
1.	Copy the path name of the downloaded FASTA file and paste it under the field “Enter input pathname for the fasta file:”
2.	Copy the pathname of the folder containing “1.txt”, “2.txt” and “3.txt” and paste it under the field “Enter input folder pathname containing surface accessibility (ASA) values:”
3.	Copy the pathname of the blank output folder and paste it under the field “Enter output pathname:”

•	Click on “Submit” to process the results. If you want to quit the window, click on “Quit”. Note that during the time of execution of the process, the window cannot be quit; it can only be done before the start of the process or after the outputs in the output folder gets produced completely. The indication that the process of execution has completed will be shown in the progress bar.

•	After clicking “Submit”,  the software groups each and every sequence present in the FASTA file into folders based on their length after removing all possible instances of unknown amino acid characters from the sequence. The software automatically names each folders based on the length of those sequences whose information are present inside it. In each of these folders, two files are created – “coord.csv” and “record.csv”.

•	“record.csv” lists all the sequences from the FASTA file, of length equal to the name of that folder inside the output folder path. The csv file also contains information about their accession ID and their protein radius values (based on Nandy graphical system: https://content.iospress.com/articles/in-silico-biology/isb00389) to give the conservativeness (PV) of all the 12-length windows considered from the sequence. The software automatically selects the folder with length same as that of the RefSeq and opens its “record.csv” file to retrieve the PV values.

•	The software performs a moving average on the surface exposure values across all the positions in the sequence entered for SABLE and produces an average solvent accessibility (ASA) value for all the 12-length consecutive peptide stretches (For more information, refer to the links for the research articles given above). Now the 2D Polygon method is used to compare the PV and ASA values for each of these 12-length peptides and determines a rank list, which ranks them based on high ASA (i.e., high exposure) and low PV (i.e., high conservativeness). The user now has to access the csv file named “best_results.csv” which contains the rank list.

PLEASE NOTE THAT THE DOWNLOADED FASTA FILE MUST CONTAIN THE REFERENCE SEQUENCE OTHERWISE THE SOFTWARE WILL NOT BE ABLE TO DECIDE WHICH SEQUENCE SHOULD BE USED AS REFERENCE.
VIOLATION IN ANY OF THE AFOREMENTIONED STEPS WILL LEAD TO AN ERROR WHICH WILL BE DISPLAYED ACCORDINGLY IN THE TERMINAL WINDOW RUNNING PARALLEL ALONG WITH THE SOFTWARE WINDOW.

For any issues or queries regarding the software, please contact us:
Subhamoy Biswas – Email: subhab365@gmail.com
Dr. Ashesh Nandy – Email: anandy43@yahoo.com
Also if possible, please don’t forget to send your valuable suggestions to the above contacts for improving the software.
