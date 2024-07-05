# Genetics10
This is the repository for an academic use software. It enables high school students to play with various functions and learn about genomics and biology. There is no previous knowledge needed and its an easy to use interface.

The code enables students to traslate DNA string into RNA or into Aminoacids, following the biological procedures. It also has severeal addition functions such as comparison between strings or generation of mutations. It is a tool for students to play and create their own code.

## Code's functions and how to use them
First, you must run the first cell to initilize the biogen library. After you have runned that cell you can collapse it by clicking the blue bar to the left. I recommend you to read this guide before starting to code. Once you are ready to go, you can code in the cells below the example. To use any of the available functions you can call them this way:
```python
rna = biogen.dna2rna(dna)
```
Type ```biogen.function()``` to call any function. Remember to provide the appropiate argument inside the brackets. The code snippet in the example above calls the function ```dna2rna()```. It gives the string ```dna``` as input, and the function returns the output called ```rna```.

The available function are the following:
1. dna2rna(string)
    Transcribes the provided DNA string into a RNA string by changing the bases (A->U, T-> A, C->G, G->C).
   
2. rna2amino(string)
    Transcribes the provided DNA string into an aminoacid string by reading codons (3x bases) and using the catalog.

3. dna2amino(string)
    Transcribes DNA strings directly to aminoacids strings, it's a merge of the dna2rna and rna2amino methods.

4. compare(string1, string2)
    Compares the strings (regardless if DNA, RNA, or aminoacids), it always return a boolean and a string. True if both strings are identical, or False and where do the string differ.

5. check(string)
    It checks if the provided string is a valid DNA or RNA string. It does not check for aminoacid strings.

6. read_input(string)
    Used to open files if a path instead of a DNA string is provided as input.

7. createmutation(string)
    Returns a new string with a mutation (only 1 per run). The mutation can change a base, erase a base or add a new one in any position.


## Tips for coding beginners
As stated above, no previous knowledge in coding is required. Therefore, we will explain some basic concepts here.
We use Jupyter Notebook to deliver this software to everybody. This is a platform that enables running code online and without installing or downloading anything. You only need to open the [link]([https://www.example.com](https://nbviewer.org/github/joanalnu/Genetics10/tree/main/)) and start playing.

The program is coded in Python (a language). Let's dive into an example of using the code. First we want to provide a DNA string to be translated. We'll call it my_dna:
```python
my_dna = 'TACACTTGACTTATCATT' # string must be between this ones ''
```
Next we'll translate this DNA string into RNA. Biologically this process is conducted inside the cell's nucleus. To simulate that we will use the ```dna2rna()``` function as shown next:
```python
my_rna = dna2rna(my_dna)
```
Let's divide this line of code into parts. First we declare the new variable ```my_rna```, which is the results of calling the function ```dna2rna()```. Inside the bracket of the function we insert the input that the function needs, in this case the DNA string we created before called ```my_dna```.

Now that we have the RNA string, let's transcribe it into an aminoacid sequence, which in a cell would configure a protein. To do so we can call the ```rna2amino()``` function as follows:
```python
my_aminoacids = rna2amino(my_rna)
```
Finally, we wwant to see our results. Therefore, we will use a Python method called ```print()``` to show our results:
```python
print(my_aminoacids)
```
If you run this code on the Jupyter Notebook, you will obtain the aminoacid sequence for the DNA string you provided. Now that you know about the basics of coding, you can start to play with these and the other functions. If you have further doubts or questiosn ask your teacher for help (or if you're a teacher you can contact me at [joan.alcaide@dsbarcelona.com](mailto:joan.alcaide@dsbarcelona.com)).
