# Information-Retrieval-System
This code is an implementation of an inverted index, a data structure used in information retrieval systems to store a mapping from content terms to the documents that contain them. Here's a breakdown of the code:

1.Document Structure:
It defines a structure named Document with two members: an integer id to represent the document ID and a character array content to store the document's content.

2.Inverted Index Node Structure:
It defines a structure named InvertedIndexNode to represent a node in the inverted index.
Each node contains:
    term: a character array to store the term.
    documentId: an integer to store the ID of the document containing the term.
    next: a pointer to the next node in the linked list.

3.Function addDocumentToIndex:
This function adds a document to the inverted index.
It takes the address of the index pointer, a term, and a document ID as arguments.
It dynamically allocates memory for a new node, copies the term and document ID into the node, and inserts it at the beginning of the linked list.

4.Function searchDocuments:
This function searches for documents containing a specific term in the inverted index.
It takes the index pointer and a term as arguments.
It iterates through the linked list, printing the document IDs where the term is found.

5.Main Function:
  It creates an array of Document structures containing sample documents.
It initializes an inverted index pointer (index) to NULL.
It iterates through the documents, tokenizes the content, and adds each token along with its document ID to the inverted index.
It prompts the user to enter a specific term and then searches for documents containing that term.
It frees the memory allocated for the inverted index linked list.

6.Tokenization and Indexing:
The content of each document is tokenized using strtok to extract individual words.
Each token is added to the inverted index along with the corresponding document ID.

7.Memory Deallocation:
Before the program exits, it deallocates the memory allocated for the inverted index linked list to prevent memory leaks.

Overall, this code demonstrates a basic implementation of an inverted index for searching documents based on terms present in them.
