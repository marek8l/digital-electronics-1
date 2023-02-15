# Lab 2: Marek IVAN

### 2-bit comparator

1. Karnaugh maps for other two functions of 2-bit comparator:

   Greater than:

   ![K-maps](https://github.com/marek8l/digital-electronics-1/blob/main/02-logic/k-mapa1.PNG)

   Less than:

   ![K-maps](https://github.com/marek8l/digital-electronics-1/blob/main/02-logic/k-mapa2.PNG)

2. Mark the largest possible implicants in the K-map and according to them, write the equations of simplified SoP (Sum of the Products) form of the "greater than" function and simplified PoS (Product of the Sums) form of the "less than" function.

   ![Logic functions](https://github.com/marek8l/digital-electronics-1/blob/main/02-logic/rovnice.PNG)

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: 30

```vhdl
      p_stimulus : process
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;

        -- First test case
        s_b <= "0011"; -- 3
        s_a <= "0000"; -- 0
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '1') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '0'))
        -- If false, then report an error
        report "Input combination b=0011 a=0000" severity error;
        
                -- Second test case
        s_b <= "0100"; --5
        s_a <= "0011"; --3
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '1') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '0'))
        -- If false, then report an error
        report "Input combination b=0100 a=0011" severity error;
        
        
                -- Third test case
        s_b <= "0100"; -- 4
        s_a <= "0110"; -- 6
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        report "Input combination b=0100 a=0110" severity error;
        
        
                -- Fourth failed test case
        s_b <= "0011"; -- 3 
        s_a <= "0111"; -- 7
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '1') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        report "Input combination b=0011 a=0111" severity error;
        
        
        

        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait;
    end process p_stimulus;
        
        
        
        
end architecture testbench;
```

2. Link to your public EDA Playground example:

   [https://www.edaplayground.com/x/uZTX](https://www.edaplayground.com/x/uZTX)
