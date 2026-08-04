# Exp 02 Word Count using MapReduce

Date:04.08.2026

## AIM:
To implement the Word Count program using the MapReduce programming model and determine the frequency of each word in the given input text.

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create a Python/Java project in the preferred IDE (Eclipse/IntelliJ IDEA/VS Code).

### Step 3:
Create the Python/Java program for the Word Count application using the MapReduce concept.

### Step 4:
Implement the **Mapper** phase to read the input text and emit each word as a key with a value.

### Step 5:
Implement the **Shuffle and Sort** phase to group identical words together.

### Step 6:
Implement the **Reducer** phase to sum the values associated with each word and calculate its total frequency.

### Step 7:
Compile and execute the program.

### Step 8:
Verify and display the word frequencies.

## PROGRAM:
```
text = "Hello world hello world mapreduce"

def mapper(text):
    words = text.lower().split()
    return [(word, 1) for word in words]

def shuffle_sort(mapped):
    shuffled = {}
    for word, count in mapped:
        if word not in shuffled:
            shuffled[word] = []
        shuffled[word].append(count)
    return shuffled

def reducer(shuffled):
    reduced = {}
    for word, counts in shuffled.items():
        reduced[word] = sum(counts)
    return reduced

mapped = mapper(text)
print("Mapper Output:")
print(mapped)

shuffled = shuffle_sort(mapped)
print("\nShuffle & Sort Output:")
print(shuffled)

reduced = reducer(shuffled)
print("\nReducer Output:")
for word, count in reduced.items():
    print(word, ":", count)
```

## OUTPUT:

<img width="1073" height="713" alt="image" src="https://github.com/user-attachments/assets/92dc97f9-4e8f-414e-afbb-67fd1b0ea987" />


## RESULT:

The Word Count program using the MapReduce programming model was implemented successfully, and the frequency of each word in the given input text was computed correctly.
```
