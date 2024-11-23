# Huffman Coding

Programming Assignment 3 for the Data Structures course  
[Assignment Link](https://ds.cs.rutgers.edu/assignment-huffman-coding/)

## Problem Description

Huffman coding is a lossless data compression algorithm invented by David A. Huffman. It compresses data by assigning variable-length codes to input characters, with shorter codes assigned to more frequent characters. The goal of this project is to apply Huffman coding to text file compression.

Computers store data as bytes, and each byte consists of 8 bits, representing a value from 0 to 255. For example, English text is typically encoded using the **ASCII** standard, where each character corresponds to a specific byte value. However, this method can be inefficient, as it uses 8 bits for every character, even if some characters are much more common than others.

In the example of the text "A b ????", the ASCII encoding results in the following byte sequence: `65 32 98 32 63 63 63 63`, which takes up 64 bits (8 characters * 8 bits). 

In contrast, Huffman coding allows us to represent these characters with shorter binary codes, like:
- `? = 0`
- `[space] = 10`
- `A = 110`
- `b = 111`

By doing so, the same text string "A b ????" can be represented in just 14 bits, significantly reducing the size compared to the 64 bits required by ASCII.

This project implements the Huffman coding algorithm to compress text files by constructing an optimal binary tree for character encoding.

## Solution Overview

The program reads a text file and applies the Huffman coding algorithm to generate a compressed file. It works by:
1. Counting the frequency of each character in the input file.
2. Building a **Huffman tree** where more frequent characters have shorter codes.
3. Encoding the input text using the binary codes from the tree.
4. Storing the compressed text in a more efficient binary format.

This algorithm minimizes the number of bits needed for encoding while avoiding wasted space for infrequently occurring characters. The resulting compressed file is smaller in size, making it ideal for efficient storage and transmission.

### Time Complexity

The overall time complexity of the program is **O(n)**, where **n** is the number of characters in the input text file. This includes the time to count character frequencies, build the Huffman tree, and encode the text.

## Key Features

- **Efficient Compression**: Uses Huffman coding to reduce the size of text files by assigning variable-length codes based on character frequencies.
- **Lossless**: The compression is lossless, meaning no data is lost during the process, and the original file can be fully reconstructed.
- **Fast Processing**: Operates in linear time complexity (O(n)), making it efficient for large files.
