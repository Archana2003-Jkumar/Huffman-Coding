# Huffman-Coding
## Aim
To implement Huffman coding to compress the data using Python.

## Software Required
1. Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required packages.
### Step2:
Create a class nodetree and do the operation.

### Step3: 
Create a function and count the frequency.

### Step4:
Print the output using while loop.

### Step5:
Display the results and end the program.

 
## Program:
```
# Get the input String
```
```
string = 'from robomaster import robot'
```
```
# Create tree nodes
```
```
212221230007 Archana priya
class NodeTree(object):
    
    def __init__(self,left=None,right=None):
        self.left = left
        self.right = right
    def children(self):
        return(self.left,self.right)

```
```
# Main function to implement huffman coding
```
```
def huffcodetree(node, left=True,binString=''):
        if type(node) is str:
            return{node : binString}
        (l,r) = node.children()
        d = dict()
        d.update(huffcodetree(l,True,binString + '0'))
        d.update(huffcodetree(r,False,binString + '1'))
        return d
        
```
```
# Calculate frequency of occurrence
```
```

freq = {}
for c in string:
    if c in freq:
        freq[c] += 1
    else:
        freq[c] = 1
freq = sorted(freq.items(),key = lambda x: x[1],reverse = True)
nodes = freq
```
```
# Print the characters and its huffmancode
```
```
while len(nodes)>1:
    (key1 , c1) = nodes[-1]
    (key2 , c2) = nodes[-2]
    nodes = nodes[:-2]
    node = NodeTree(key1 , key2)
    nodes.append((node, c1+c2))
    nodes = sorted(nodes, key = lambda x:x[1], reverse = True)
    
    huffmancode = huffcodetree(nodes[0][0])

print(' Char|Huffman code')
print('--------------------')

for(char,frequency) in freq:
    print('%-4r | %12s' % (char,huffmancode[char]))

```
## Output:
### Print the characters and its huffmancode
![image](https://github.com/Archana2003-Jkumar/Huffman-Coding/assets/93427594/46204048-15b4-45d7-94f9-77c888113e99)

## Result
Thus the huffman coding was implemented to compress the data using python programming.
