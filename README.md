# Genetics10
[Genetics10](https://joanalnu.github.io/genetisc10) is a tool designed to help students learn about general genomics through easy-to-use software. It enables students to explore various functions and gain knowledge about genomics and biology without requiring any prior experience. The interface is user-friendly and accessible to all.

The software allows students to translate DNA sequences into RNA or amino acid sequences, following the standard biological processes. It also includes several additional features, such as comparing sequences, generating mutation, or iterating. Furthermore, there is an integration with the AlphaFold API, allowing users to visualize predicted protein structures, as well as as functions to simulate the action of CRISPR-Cas9 gene editing. Genetics10 is a powerful tool for students to experiment with, learn from, and even create their own code.

(jump to the info for educators below)

## How to use the code
This is a Jupyter Notebook based software, which makes it easy to yse as it does not require any installations. You can simply open the notebook on the browser and start coding right-away. Before starting you can decide which tool to use: Jupyter Lab online or Google Colab. both are free browser-based tools that enable you to open, edit, and run Jupyter Notebooks. See the next section for [Jupyter  Lab online](#how-to-use-jupyter-lab-online) and [Google Colab](#how-to-use-google-colab) tutorials.

### How to use Jupyter Lab online
First, go to the [project's GitHub](https://github.com/joanalnu/genetics10) and download the files by clicking the ```code```button (you can also clone the repository). If you download the ZIP don't forget to decompress it.

![Image of GitHub download button](https://github.com/joanalnu/genetics10/raw/main/pictures/githubbutton.png)

Next open Jupyter Lab online (this is a platform from Jupyter that enables you to open Notebooks in your browser) with this link: [https://jupyter.org/try-jupyter/lab/](https://jupyter.org/try-jupyter/lab/). You should open a browser tab like this:

![Image of Jupyter Lab browser tab](https://github.com/joanalnu/genetics10/raw/main/pictures/jupyterlab.png)

In this tab, go to the left-handed panel, where you can see the files. Click to the upload button and upload the files you want from the ```genetics10``` folder in your device (whereever you have download it). The file with the extension ```ipynb``` is the file you will use to run the code. You will need to download one of the copies, choose by your language preferences.

![Image of files upload](https://github.com/joanalnu/genetics10/raw/main/pictures/filesupload.png)

Note that if you also upload the ```README.md``` file you must overwrite jupyterlab's ```readme.md``` file. Once you have uploaded your files you only need to open them (double-click to open file).

![Image of opened file](https://github.com/joanalnu/genetics10/raw/main/pictures/openedfile.png)

You can now read [next section](#codes-functions-and-how-to-use-them), which explains how to use the ```gen10``` functions.

### How to use Google Colab
This section shows how to open the Genetics10 documents in the Google Colab environment. If you had already opened Genetics10 in Jupyter Lab, you can skip this section and jump to [the next section](#codes-functions-and-how-to-use-them).

Google Colab is a  free platform that allows you to run Jupyter Notebooks in the cloud. First, open a new colab notebook in [colab.research.google.com](https://colab.research.google.com) as in the next video.

![Video of Opening a New Colab Notebook](https://github.com/joanalnu/raw/pictures/openingColab.gif)

Next, you need to clone the Genetics10 GitHub Repository into this space. Do so by running the following code line in a cell: ```!git clone https://github.com/joanalnu/genetics10.git```.

![Cloning GitHub Repository](https://github.com/joanalnu/genetics10/raw/picture/cloningGitHub.gif)

Finally, you can go to the folder icon in the menu-bar on the left and open the document (```ipynb``` documents are the code in different languages) on your preferred language.

Great! Now you can continue to the [next section](#codes-functions-and-how-to-use-them), which explain how to use the ```gen10``` functions.

## Code's functions and how to use them
First, you must run the first cell to initilize the ```gen10``` class. You can do that by pressing ```shift+enter``` or pressing the run button in the upper toolbar. After you have runned that cell you can collapse it by clicking the blue bar to the left. 

![Initializing gen10 class](https://github.com/joanalnu/genetics10/raw/main/pictures/initialize_gen10.gif)

I recommend you to read this guide before starting to code. Once you are ready to go, you can code in the cells below the example. To use any of the available functions you can call them this way:
```python
rna = gen10.dna2rna(dna)
```
Type ```gen10.function()``` to call any function. Remember to provide the appropiate argument inside the bracketss. The code snippet in the example above calls the function ```dna2rna()```. It gives the string ```dna``` as input, and the function returns the output called ```rna```.

The available functions are the following:
1. ```dna2rna()```\
    Transcribes the provided DNA string into a RNA string by changing the bases (A->U, T-> A, C->G, G->C).\
   Argument: ```string```\
   Output: ```string```
   
2. ```rna2amino()```\
    Transcribes the provided DNA string into an aminoacid string by reading codons (3x bases) and using the catalog.\
   Argument: ```string```\
   Output: ```string```

3. ```dna2amino()```\
    Transcribes DNA strings directly into aminoacids strings, it's a merge of the dna2rna and rna2amino methods.\
   Argument: ```string```\
   Output: ```string```

4. ```compare()```\
    Compares the strings (regardless if DNA, RNA, or aminoacids), it always returns a boolean and a string. True if both strings are identical, or False and where do the string differ.\
   Argument: ```string1, string2```\
   Output: ```boolean, string```

5. ```check()```\
    It checks if the provided string is a valid DNA or RNA string. It does not check for aminoacid strings.\
   Argument: ```string```\
   Output: ```string```

6. ```read_input()```\
    Used to open files. The full path to the file must be saved in the same folder as this file and can have only 1 sequence.\
    Argument: ```string```\
    Output: ```string```

7. ```createmutation()```\
    Returns a new string with a mutation (only 1 per run). The mutation can change a base, erase a base or add a new one in any position.\
    Argument: ```string```\
    Output: ```string```

8. ```iterate()```\
    By  inputting a list of inputs and a list of functions it returns a table with all the results for each functions and input.
    Argument: ```list, list```
    Outpu  ```dataframe``` (table)
   
9. ```tosingle()```\
    Transcribes an aminoacid string from three-letter code to single-letter code.\
    Argument: ```string```\
    Output: ```string```

10. ```alphafold_prediction()```\
   By inputting a UniProt ID $^1$ , it returns a url to the ```pbd``` file of the predicted protein's structure.\
   Argument: ```string```\
   Output: ```dictionary```\

11. ```generate_protein()```\
     By inputing the resulting dictionary of ```alphafold_prediction()``` it returns a visualization of the predicted protein's strucutre.\
    Argument: ```dictionary```\
    Output: ```None```

12. ```cut_dna(string, integer)```\
    Cuts the DNA string into two parts at the specified position.\
    Argument: ```string and integer```\
    Output: ```string``` Original DNA with a marked cut

13. ```repair_dna(string, integer, string, string)```
    Repairs a cut DNA string by either deleting a base (NHEJ) or adding specific bases at the specified location (HDR).\
    Argument: ```string``` DNA string\
            ```integer``` cut position\
            ```string``` type of repair (NHEJ or HDR)\
            ```string``` Optional: string to insert by HDR repair\
    Output: ```string``` Repaired DNA

**X.** ```download_pdb()```\
   Internal function which enables ```generate_protein``` to work. Basically it retrieves the structure data from the url.

$^1$ The Alphafold API only admits UniProt IDs as input. You can find the UniProt ID of a protein or gene in the web. We recommend the following databases.
1. Official UniProt website: [https://www.uniprot.org](https://www.uniprot.org)
2. For genes: [https://www.ensembl.org/Multi/Tools/Blast](https://www.ensembl.org/Multi/Tools/Blast)
3. UniProt are available in the alpahfold website itself: [https://alphafold.ebi.ac.uk](https://alphafold.ebi.ac.uk)

 Please, note that a step-for-step guide on how to access UniProt IDs is comming soon.

## Tips for coding beginners
As stated above, no previous knowledge in coding is required. Therefore, we will explain some basic concepts here.
We use Jupyter Notebook to deliver this software to everybody. This is a platform that enables running code online and without installing or downloading anything. You only need to open the [link](https://jupyter.org/try-jupyter/lab/), upload the files and start playing.

The program is coded in Python (a language). Let's dive into an example of using the code. First we want to provide a DNA string to be translated. We'll call it my_dna:
```python
my_dna = 'TACACTTGACTTATCATT' # string must be between this ones ''
```
Next we'll translate this DNA string into RNA. Biologically this process is conducted inside the cell's nucleus. To simulate that we'll use the ```dna2rna()``` function as shown next:
```python
my_rna = dna2rna(my_dna)
```
Let's divide this line of code into parts. First, we declare the new variable ```my_rna```, which is the result of calling the function ```dna2rna()```. Inside the brackets of the function we insert the input (argument), this is the information that the function requires, in this case the DNA string we created before called ```my_dna```.

Now that we have the RNA string, let's transcribe it into an aminoacid sequence, which in a cell would configure a protein. To do so we call the ```rna2amino()``` function as follows:
```python
my_aminoacids = rna2amino(my_rna)
```
Finally, we want to see our results. Therefore, we will type our variable to be shown:
```python
my_aminoacids
```
If you run this code on the Jupyter Notebook, you will obtain the aminoacid sequence for the DNA string you provided. Now that you know about the basics of coding with ```gen10```, you can start to play with these and the other functions. If you have further doubts or questions ask your teacher for help.


## Info for educators
### How can I use this in my class?
First, identify in your curriculum where you can integrate the software, which is already built aligned with the general education guidelines. Then you should start by explaining the fundamental concepts of genomics in your biology or science class, as you would do normally. Then you can introduce this tool to students and explain how to use it.

You can use the software to design problem solving challenges that require students to use critical thinking and coding skills. For example, a scenario where a gene mutation causes a disease, and ask students to write code that identifies and corrects the mutation. This type of activities foster creativity and problem-solving skill and led further to more science like CRIPSR-Cas9.

Also, perform planned activities where students apply what they've learned in real life. Create assignments where students write simple code using the pre-established functions to emulate genetic processes such as transcription and translation.

By providing step-by-step instructions students will have better chances of understanding the biological content and a better usage of the full potential of this tool. Moreover, providing by integrating real-world examples and application in genomics and biotechnology can increase student motivation and interest, and show and discuss modern research tools.

Finally, you can also adopt a flipped classroom approach by assigning software tutorials as homework and use class time for interactive and applied learning. This allows for maximized classroom engagement and allows for more personalized instruction.

Encouraging collaboration by planning group projects, students can work together to solve more complex problem. And collaborative projects fosters teamwork and allow students to learn from each other.

By incorporating these strategies, you can effectively use this software to enhance your biology curriculum, engage students, and foster a deeper understanding of both genomics and coding.

### Why should I use this in my class?
This is a useful resource for students to learn both genomics and basic coding. On the one hand, this is a powerful tool that enables students to apply what they have learned regarding biology. It is made to be interactive and customizable and anyone can run their own code without knowledge of coding. On the other hand, students will learn and get first-hand experience with bioinformatics and computation. Coding is an essential skill for future workers, regardless their field.

Further, the fact that it is web-based and does not need any installation makes it perfect for school managed devices and enables usage regardless of operating system. It also fosters a teamwork and communication skills, as projects can be done in collaboration.

Additionally, the features of the software are aligned with the scholar curriculum and it shows practical applications of classroom content right away. It also promotes critical thinking by allowing students to write their own code to solve problems and engage actively. And prior knowledge of coding is not required at all, as students will use the pre-established functions that enable a wide range of possibilities. Further, students can adapt their code to their problems or write new functions. The code is easily scalable and has endless possibilities!

### Contact me!
If you have further doubts, feel free to contact me at [joanalnu5@gmail.com](mailto:joanalnu5@gmail.com). I'm also open to schedule meetings or calls.

Please note that work is underway for more translations.
