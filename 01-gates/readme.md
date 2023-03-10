# Lab 1: Marek IVAN

### De Morgan's laws

1. Equations of all three versions of logic function f(c,b,a):

   ![Logical function](https://github.com/marek8l/digital-electronics-1/blob/main/01-gates/Rovnice.PNG)

2. Listing of VHDL architecture from design file (`design.vhd`) for all three functions. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
architecture dataflow of gates is
begin
    f_orig_o <= (not(b_i) and a_i) or
                (c_i and not(b_i or not(a_i)));
    f_nand_o <= (not(b_i) nand a_i) nand(c_i nand (not(b_i)and a_i)); -- MODIFY THIS FUNCTION
    f_nor_o  <= (not((b_i) nor not(a_i))) nor (not(c_i) nor not((not(b_i) nor (a_i)))) ;  -- MODIFY THIS FUNCTION
end architecture dataflow;
```

3. Complete table with logic functions' values:

   | **c** | **b** |**a** | **f_ORIG** | **f_(N)AND** | **f_(N)OR** |
   | :-: | :-: | :-: | :-: | :-: | :-: |
   | 0 | 0 | 0 | 0 | 0 | 0 |
   | 0 | 0 | 1 | 1 | 1 | 1 |
   | 0 | 1 | 0 | 0 | 0 | 0 |
   | 0 | 1 | 1 | 0 | 0 | 0 |
   | 1 | 0 | 0 | 0 | 0 | 0 |
   | 1 | 0 | 1 | 1 | 1 | 1 |
   | 1 | 1 | 0 | 0 | 0 | 0 |
   | 1 | 1 | 1 | 0 | 0 | 0 |

### Distributive laws

1. Screenshot with simulated time waveforms. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

![Logical function](https://github.com/marek8l/digital-electronics-1/blob/main/01-gates/prubeh1.PNG)
![Logical function](https://github.com/marek8l/digital-electronics-1/blob/main/01-gates/prubeh2.PNG)

2. Link to your public EDA Playground example:

  De Morgan's laws: https://www.edaplayground.com/x/7y5j
  ......
  Distributive laws: https://www.edaplayground.com/x/9jxk
