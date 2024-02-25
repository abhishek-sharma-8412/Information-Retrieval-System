#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Define a structure to represent a document
typedef struct {
    int id;
    char content[1000];
} Document;

// Define a structure for an inverted index node
typedef struct InvertedIndexNode {
    char term[50];
    int documentId;
    struct InvertedIndexNode* next;
} InvertedIndexNode;

// Function to add a document to the inverted index
void addDocumentToIndex(InvertedIndexNode** index, char term[], int documentId) {
    InvertedIndexNode* newNode = (InvertedIndexNode*)malloc(sizeof(InvertedIndexNode));
    strcpy(newNode->term, term);
    newNode->documentId = documentId;
    newNode->next = *index;
    *index = newNode;
}

// Function to search for documents containing a specific term
void searchDocuments(InvertedIndexNode* index, char term[]) {
    printf("\nSearching for documents containing '%s':\n", term);
    while (index != NULL) {
        if (strcmp(index->term, term) == 0) {
            printf("Document ID: %d\n", index->documentId);
        }
        index = index->next;
    }
}

int main() {
    // Create an array of documents
    Document documents[3];
    documents[0].id = 1;
    strcpy(documents[0].content, "This is a sample document.");

    documents[1].id = 2;
    strcpy(documents[1].content, "Document 2 contains relevant information.");

    documents[2].id = 3;
    strcpy(documents[2].content, "Document 3 is another example document.");

    // Build the inverted index
    InvertedIndexNode* index = NULL;

    for (int i = 0; i < 3; i++) {
        char* token = strtok(documents[i].content, " ");
        while (token != NULL) {
            addDocumentToIndex(&index, token, documents[i].id);
            token = strtok(NULL, " ");
        }
    }
     // Search for documents containing a specific term
    char s[100];
    printf("\nEnter the specific term :");
    gets(s);
    searchDocuments(index,s);
    // Free the memory allocated for the inverted index
    while (index != NULL) {
        InvertedIndexNode* temp = index;
        index = index->next;
        free(temp);
    }

    return 0;
}

    
