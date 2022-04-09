# HuffmanCoding

Programming Assignment 3 for Data Structures course

https://ds.cs.rutgers.edu/assignment-huffman-coding/

## Problem

David Huffman invented an algorithm that constructs the code called the Huffman code to compress data. That is, given some data, it can express the same information using less space. This project specifically focuses on compressing text files.

Computers store data as a sequence of bytes. A byte consists of eight bits, and it represents a value between 0 and 255 inclusive. To represent English text, we need a way of assigning each English letter, punctuation symbol, special character, etc. to a sequence of eight bits (a value from 0 to 255). This mapping is provided by the ASCII encoding. 

For instance, consider the text “A b ????”. This is represented as the following sequence of bytes: “65 32 98 32 63 63 63 63”. Note that the space counts as a character, and its value in the ASCII encoding is 32. If we write out the binary string for each character according to the table above and concatenate them together, we get “0100000100100000011000100010000000111111001111110011111100111111”. Storing our original string with the ASCII encoding requires 8*8 =_ 64 bits. There are 8 characters in the text “A b ????” and each character is represented by a byte that is 8 bits long. 

Now, imagine if we weren’t forced to use eight bits for every character, and we could instead use the binary encoding “? = 0, [space] = 10, A = 110, b = 111”. Then our string “A b ????” would become “11010111100000”. This is only 14 bits, significantly smaller than the 64 bits that ASCII requires. Also notice that none of these codes are a prefix of any others, so there is no ambiguity when decoding. Here, we compressed our string by finding a different encoding for the characters that minimized the number of bits we needed to use. This is the essence of the Huffman coding algorithm. 

## Solution

This program can convert a text file into a smaller file in n time complexity. Not only does it avoid wasting space encoding characters that don’t appear very often, but it also makes sure that the characters which appear the most often receive the shortest codes.
