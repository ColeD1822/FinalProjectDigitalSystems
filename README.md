# FinalProjectDigitalSystems
Tutorial on how to convert a number from decimal to IEEE 754 floating point representaion 

# How to convert decimal numbers to single precision IEEE 754 floating point
#### By: Cole Dennis

- [Summary and Purpose](#summary-and-purpose)
- [Target Audience](#target-audience)
- [Step 1](#step-1)
- [Step 2](#step-2)
- [Step 3](#step-3)
- [Step 4](#step-4)
- [Step 5](#step-5)
- [Step 6](#step-6)
- [Step 7](#step-7)
- [Step 8](#step-8)
- [Step 9](#step-9)


## Summary and Purpose
Computers use a base 2 number system which is why we change numbers from a 10 base system to IEEE 754 which is what a computer will understand when working with floats. Many differnet programming languages use IEEE 754 when dealing with float numbers so it is important to understand how to convert numbers we work with so we have a general understanding on how a computer is working with the information we are providing to it. A base 10 number system is what we as humans see everyday which are numbers represented from 0 to 9 unlike the base 2 system which only uses 0 and 1. 

This tutorial will give a number with a base of 10 and will show the steps breaking it down into the base 2 number system and will then show the steps to converting into IEE 754 so the reader will have a better understanding on how to convert base 10 numbers. 

## Target Audience
The target audience for this tutorial are students who already know how to convert numbers to binary and want or need to learn how to convert numbers to IEEE 754 for projects or general knowledge of the subject. 

## Step 1 
Single precision conversion uses 32 bits compared to double precision which uses 64 bits. This means that our conversion will be represented by 32 bits or thirty two 0 and 1's. We start by picking a number to convert. For this example we will be converting the number 72.25. 

Since our number is 72.25, we have to seperate the whole number and decimal. In our case, the whole number is 72 and the decimal is 0.25. 

## Step 2
We now need to convert the whole number which is 72 into binary. To do this step we *take 72 and divide by 2*. The number we get is 36. This number doesn't have a remainder so in binary our **first number is 0**. We then *take 36 and divide by 2*. The next number we get is 18 with no remainder which means that **our next number is 0**. Then, we *take 18 and divide by 2* which is 9 so again **we get a 0**. We then *divide 9 by 2* and get 4.5. We have a remainder which means that **we will represent this number with 1 in binary**. After this, we *take 4 and divide by 2*. This gives us 2 so we **represent it with 0**. Our second to last step is to *divide 2 by 2* which is 1 so we will **represent it with 0**. Our last step is to *divide 1 by 2* which is 0.5 so we **represent it with 1**. 

This means that 72 in binary is 0001001.

## Step 3 
Our next step is to convert the decimal part of our number to binary. To start, we will take 0.25 and multiply by 2. We get 0.5 which is represented by a 0 in binary. We then take 0.5 and multuply it by 2. We then get 1.0 which is represented by a 1 in binary. We then take 0.0 from the decimal we just got from 1.0 and multiply it by 2 to see if we continue getting more numbers. We end up with 0 which means we end our calculations. 

This means that 0.25 in binary is 0.01.

## Step 4
We now combine the 2 binary numbers we have. For this example, the answer would be 0001001.01 

## Step 5 
For step 6, we have to convert the number into scientific notation with the base of 2. To do this, we take our number in binary which is 0001001.01 and move the decimal place to the right of the first bit. We have to **move the decimal 6 places** which means that we have a **power of 6**. Moving the decimal to the left which is what we did shows that our exponent will be positive. 

So, our number is now 00.00100101*2^6.

## Step 6
We now have to determine the first number of our IEEE 754 single precision representation. To do this, we see if the number we've been working with is positive or negative. **Our number is 72.25 which is positive so the number we represent that with is 0 in binary**. If our number was negative, we would represent it with 1 in binary. 

## Step 7 
We now know the starting point of our IEEE 754 single precision representaion which is 0. we now have to represent the exponent in binary to continue working on getting to the end result. For single recision, the exponent bias is 127 which is used for every single precision problem. **We take 127 and add 6 to is which is 133**. Next, have to **take 133 and convert it to binary**. We do this by taking *133 and dividing 2 which is 66.5*. There is a remainder in 66.5 so we **represent this with a 1**. Now, we *take 66 and divide by 2*. The answer is 33 so we **represent it with a 0**. Next, *take 33 and divide by 2* which is 16.5. We **represent this number with a 1**. Then, *take 16 and divide by 2* which is 8 so we **represent this with a 0**. After this, *take 8 and divide by 2* which is 4 so this is **represented by a 0** as well. Now, we take *4 and divide by 2* which is 2 so we **represent this with 0**. The second to last step is to *take 2 and divide by 2* which is 1 so we **represent this with a 0**. The final step is to *take 1 and divide by 2* which is 0.5 so we **represent this with a 1**. 

So converting 133 to binary, we get 10000101. This means that **so far in our IEEE 754 conversion we have 010000101**.

## Step 8 
The second to last step, we take the decimal from the scientific notation we have converted earlier in this tutorial and we put it into our IEEE 754 conversion. The number we have is 00.00100101*2^6. All we need to do in this step is take 00100101 from this and put it into our IEEE 754 conversion which is 10000101. 

**We put 00100101 behind the exponent** we just converted in the IEEE 754 conversion. **The IEEE 754 conversion number will now be 01000010100100101** with the decimal place of the scientific notation number added to it. 

## Step 9 
The final step is to prepare the final touches to the conversion. We have the 0 at the beginning of the number because it is a positive number. Then, we have the exponent converted to binary which **makes our conversion 10000101**. The second to last step is to add the decimal places in the scientific notation we did earlier in the tutorial which was 00100101. We put this behind the exponent part in the conversion so **we now have 01000010100100101**. The final part is to add zeros to the IEEE 754 format so it reaches 32 bits because we have all of the information we need since we have the sign, exponent, and the decimal places all represented in our conversion. 

Our solution is 0 10000101 001001010000000000000 which represents 72.25 in IEEE 754 format. 



