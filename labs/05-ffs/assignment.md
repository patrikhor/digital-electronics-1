# Lab 5: Horčička Patrik

### Flip-flops

1. Listing of VHDL architecture for T-type flip-flop. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
architecture Behavioral of t_ff_rst is
signal q_n : std_logic;
begin

    p_t_ff_rst : process(clk)
    begin
        if rising_edge(clk) then  -- Synchronous process

                if (rst = '1') then
                    q_n <= '0';
                    q_0 <= '0';
                    q_0_bar  <= '1';
                else
                    q_n <= (t and not(q_n)) or (not(t) and q_n);
                    q_0_bar <= not((t and not(q_n)) or (not(t) and q_n));
                    q_0 <= (t and not(q_n)) or (not(t) and q_n);     
                end if;   
        end if;
    end process p_t_ff_rst;
end architecture Behavioral;
```

2. Screenshot with simulated time waveforms. Try to simulate both flip-flops in a single testbench with a maximum duration of 200 ns, including reset. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

   ![your figure](images/Capture1.PNG)

### Shift register

1. Image of the shift register `top` level schematic. The image can be drawn on a computer or by hand. Always name all inputs, outputs, components and internal signals!

   ![your figure](images/D-flipflop.png)
