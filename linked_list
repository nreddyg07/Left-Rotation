//Left rotation using linked lists
#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
#define MALLOC(p,s,t)\
		p = (t) malloc(s);\
	if (p == NULL )\
	{\
		fprintf(stderr, "Insufficient Memory\n");\
		exit(EXIT_FAILURE);\
	}

struct List {
    int val;
    struct List* next;
};

typedef struct List* NODE;

NODE createNode (NODE first,int n)
{
	for(int i=n;i>=1;i--){
	  NODE q;
	  MALLOC(q, sizeof(struct List),NODE);
	  q->val=i;
	  q->next = first;
	  first = q;
	}
	return first;
}

void printList(NODE first) {
    NODE temp = first;
    while (temp != NULL) {
        printf("%d  ", temp->val);
        temp = temp->next;
    }
    printf("\n");
}

NODE rotateLeft(NODE first, int k) {
    if (first == NULL || k == 0) 
        return first;
    int count = 1;
    NODE q1 = first;
    while (q1->next != NULL) {
        count++;
        q1 = q1->next;
    }
    k = k % count;
    if (k == 0) 
        return first;
    NODE q2 = first;
    int i = 0, j = k - 1;   
    while (i < j) {
        q2 = q2->next;
        i++;
    }
    q1->next = first;
    first = q2->next;
    q2->next = NULL;
    return first;
}

int main() {
	NODE first=NULL;
	int n,k;
    printf("Enter the number of nodes to be created: ");
	scanf("%d",&n);
	first=createNode(first ,n);
    printf("Original list: ");
    printList(first);
	printf("Enter the number of rotations to be performed by left: ");
	scanf("%d",&k);
    first = rotateLeft(first, k);
    printf("List after rotating left by %d positions: ", k);
    printList(first);
    return 0;
}
