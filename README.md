# sorting-of-numbers
## Aim
To write and execute an Assembly Language Program for sorting data in Ascending and  descending order using 8051 microcontroller on Keil software.
---

## Apparatus Required
- Personal Computer  
- Keil µVision software  
---

## Algorithm(ASCENDING ORDER)
1. Initialize the register **R7** with count (number of elements).  
2. Get the first two elements into two registers.  
3. Compare the two elements:  
   - If the value in register **R0** is lower, exchange **A** and **R0** data.  
   - Otherwise, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0** → if yes, move the register **R0 & A**.  
5. Increment pointer and decrement **R7**.  
6. If **R7 ≠ 0**, repeat from Step 2.  
7. Otherwise, stop the program.  
---

## Program (Ascending order)

```asm
ORG 0000H

MOV R1,30H        ; Outer loop count = N
DEC R1

LOOP1: MOV R0,#40H
       MOV R6,30H
       DEC R6

LOOP:  MOV A,@R0
       INC R0
       MOV B,@R0

       CJNE A,B,NEXT

NEXT:  JC DOWN        ; If A < B, no swap

       MOV @R0,A      ; Swap if A > B
       DEC R0
       MOV @R0,B
       INC R0

DOWN:  DJNZ R6,LOOP
       DJNZ R1,LOOP1

END



```
## OUTPUT(Ascending order)

<img width="960" height="500" alt="image" src="https://github.com/user-attachments/assets/ac17a26d-5277-4126-885e-0bec6a8ec8e0" />


---

## Algorithm(Descending order)
1. Initialize the register **R7** with count.  
2. Get first two elements in two registers.  
3. Compare the two elements of data:  
   - If the value of **R0** register is high, then exchange **A** and **R0** data.  
   - Else, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0**, then move the contents of **R0** and **A**.  
5. Again increment pointer and decrement **R7**.  
6. Check if **R7 = 0**:  
   - If **No**, repeat the process from Step 2.  
   - If **Yes**, stop the program.  
---
## Program (Descending order)

```asm
ORG 0000H
MOV R1,30H     ; Outer loop count = N
DEC R1

LOOP1: MOV R0,#40H
       MOV R6,30H
       DEC R6

LOOP:  MOV A,@R0
       INC R0
       MOV B,@R0
       CJNE A,B,NEXT
NEXT:  JNC DOWN

       MOV @R0,A
       DEC R0
       MOV @R0,B
       INC R0

DOWN:  DJNZ R6,LOOP
       DJNZ R1,LOOP1   ; Outer loop ends correctly

END



```
## OUTPUT(Descending order)

<img width="971" height="556" alt="image" src="https://github.com/user-attachments/assets/f64feb41-6663-4408-a652-ecae10777272" />


---
## RESULT:
Thus the sorting of given data was done using 8051 keil software.


Knowledge of the origin of feathers developed as new fossils were discovered throughout the 2000s and the 2010s, and technology enabled scientists to study fossils more closely. Among non-avian dinosaurs, feathers or feather-like integument have been discovered in dozens of genera via direct and indirect fossil evidence.[2] Although the vast majority of feather discoveries have been in coelurosaurian theropods, feather-like integument has also been discovered in at least three ornithischians, suggesting that feathers may have been present on the last common ancestor of the Ornithoscelida, a dinosaur group including both theropods and ornithischians.[3] It is possible that feathers first developed in even earlier archosaurs, in light of the discovery of vaned feathers in pterosaurs.[4][5] Fossil feathers from the dinosaur Sinosauropteryx contain traces of beta-proteins (formerly called beta-keratins), confirming that early feathers had a composition similar to that of feathers in modern birds.[6] Crocodilians also possess beta keratin similar to those of birds, which suggests that they evolved from common ancestral genes.[7][8]


Shortly after the 1859 publication of Charles Darwin's On the Origin of Species, the British biologist Thomas Henry Huxley proposed that birds were descendants of dinosaurs. He compared the skeletal structure of Compsognathus, a small theropod dinosaur, and the "first bird" Archaeopteryx lithographica (both of which were found in the Upper Jurassic Bavarian limestone of Solnhofen). He showed that, apart from its hands and feathers, Archaeopteryx was quite similar to Compsognathus. Thus Archaeopteryx represents a transitional fossil. In 1868, he published On the Animals which are most nearly intermediate between Birds and Reptiles, which made that case.[9][10]


