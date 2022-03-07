
# 4-BIT CALCULATOR WITH DISPLAY                           
                               
                           

## INTRODUCTION
                                               
A calculator is any device that performs arithmetic operations using pre-programmed logic. This project involves assembling one such machine, although simplistic in comparison to many modern calculators. The calculator is designed to do simple arithmetic operations like addition and subtraction, performed between one-digit numbers. The 4-bit calculator designed consists of 4-bit adders, counters, decoders, basic gates, switches and seven-segment displays. By limiting this project to logic circuit design concepts, the full knowledge of the digital logic design course has been harnessed in order to assemble this project. Techniques that have been taught in the course, such as simplification through Karnaugh maps, reducing expressions through Demorgan's law, and implementing Boolean expressions have all been used in tandem so that this project may become a possibility. As such, this project is based solely on design and implementation through digital logic.
___

 
## LIST OF COMPONENTS USED

| SL.NO      | NAME OF THE COMPONENTS | REQUIRED NUMBERS |
| ----       | -----                  | ---              |
|1           | IC-7490 (DECADE COUNTER) | 2              |
|2           | IC-7483 (4-BIT ADDER) | 2              |
|3           | IC-7408 (2 INPUT AND) | 1              |
|4           | IC-7486 (2 INPUT XOR) | 1              |
|5           | IC-7432 (2 INPUT OR)) | 1              |
|6           | IC-7448 (BCD TO 7 SEGMENT DECODER) | 4              |
|7           | PUSH BUTTON | 4              |
|8           | 7 SEGMENT DISPLAY | 4              |
|9           | SWITCH | 1              |

___

## WORKING
 
* ### INPUT:
The digits that are to be added or subtracted are given as push inputs using a push-button which increments on each push. The inputs given are counted with a 7490 Decade Counter whose clock pulse is the push input. The input digits are displayed correspondingly on a seven-segment display connected. A 7448 BCD to 7-segment decoder is used here. Another push button is also connected to the clear of Decade Counters to clear the input digits whenever needed.

* ### BCD ADDER/SUBTRACTOR:

We have a BCD adder circuit along with a control input. The control input is used to select a particular operation. The addend as the first 4-bit binary number is fed directly as input to the 4-bit adder. 7483 IC is used as a 4-bit adder. The augend as the second 4-bit binary number is fed as one input to each controlled inverter, i.e. the 2-input XOR gates. The other input of each of the four XOR gates is the control input which is connected to the carry-in of the adder and to a switch. When the switch is OFF, one input of each XOR gate becomes 0 and therefore the input bits given as the other input of each XOR gate is directly fed to the adder. The four output bits of the adder are connected directly to the 4 input bits of the second adder as augend. 


The addend is given in such a way that the binary number 6(0110) has to be added if the output sum of the first adder exceeds 9 (up to only which the BCD value is valid). So the first and the fourth bit of the addend is grounded and the second and third bit is connected to the output of the OR gate which is connected to the carry bit generated from the first adder, the AND output of the first and second bit of the output of the first adder and the AND output of first and third bit of the output of the first adder. So that when the output of the OR gate is 1 the addend becomes 0110 and is added to the sum to make it a valid BCD number. Above is the case of addition. Now when the switch is ON, one input of each XOR gate becomes 1 and the complement of the other input is fed to the adder. As the switch is also connected to the Cin of the adder, 1 is added along with the complement of the augend, so that the 2’s complement of the augend is added with the addend which basically becomes subtraction. Here, we want to eliminate the addition of 0110 to the output of the first adder in case a carry is generated because the difference between the given one-digit numbers will always be less than or equal to 9 which are valid BCD numbers. For this purpose instead of connecting the output of the OR gate to the second and third bit of the addend of the second adder, we add a AND gate with one input of the OR gate connected to it and another, the inverted input of the Cin. 




So that when the switch is off, its inverted output is 1 and also the output of the OR gate will be 1 so that the AND gate will generate 1 as output and 0110 will be added, whereas when the switch is ON, the inverted output will be 0 so that AND gate generates 0 as output for sure and it is connected to the second and third bit of the addend and it naturally becomes 0000, so that nothing is added to the generated output of the first adder. Hence we get two numbers subtracted.

* ### OUTPUT
The output BCD sum/ difference from the second adder is fed into 7448 decoders. Its output is directly connected to the 7-Segment displays which show the BCD outputs as decimal in 2-digits.

___

## BLOCK DIAGRAM
       






## CIRCUIT DIAGRAM

## RESULT



## CONCLUSION

 
The calculator has been implemented successfully and is cent per cent functional with respect to the objectives aforementioned. Simple arithmetic operations like addition and subtraction performed between two single-digit numbers are successfully carried out in BCD format output displayed in decimal.
