# Huffman-Coding

## Aim :

To implement Huffman coding to compress the data using Python.

## Software Required :

1. Anaconda - Python 3.7

## Algorithm :

### Step1 :

Get the input String.

### Step2 :

Create tree nodes.

### Step3 :

Main function to implement huffman coding.

### Step4 :

Calculate frequency of occurrence.

### Step5 :

Print the characters and its huffmancode.
 
## Program:

### DEVELOPED BY : ABRIN NISHA A
### REG NO : 212222230005

### Get the input String

```python
string='ABRIN NISHA 212222230005'
```

### Create tree nodes

```python
class NodeTree(object):
    def __init__(a,left=None,right=None):
        a.left=left
        a.right=right
    def children(a):
        return(a.left,a.right)
```
### Main function to implement huffman coding

```python
def huffman_code_tree(node,left=True,binString=''):
    if type(node) is str:
        return {node:binString}
    (l,r)=node.children()
    d=dict()
    d.update(huffman_code_tree(l,True,binString+'0'))
    d.update(huffman_code_tree(r,False,binString+'1'))
    return d
```

### Calculate frequency of occurrence
```python
freq={}
for c in string:
    if c in freq:
        freq[c]+=1
    else:
        freq[c]=1
freq=sorted(freq.items(),key=lambda x:x[1],reverse=True)
nodes=freq
```
```python
while len(nodes)>1:
    (key1,c1)=nodes[-1]
    (key2,c2)=nodes[-2]
    nodes=nodes[:-2]
    node=NodeTree(key1,key2)
    nodes.append((node,c1+c2))
    nodes=sorted(nodes,key=lambda x:x[1],reverse=True)
Print the characters and its huffmancode
huffmanCode=huffman_code_tree(nodes[0][0])
print('Char |Huffman code ')
print('--------------------')
for(char,frequency) in freq:
    print('%-4r |%12s'%(char,huffmanCode[char]))
```


## Output :

### Print the characters and its huffmancode

![Screenshot 2023-05-31 144442](https://github.com/Abrinnisha6/Huffman-Coding/assets/118889454/de4c842b-221c-4d03-8138-672ea9af710e)


## Result :

Thus the huffman coding was implemented to compress the data using python programming.
