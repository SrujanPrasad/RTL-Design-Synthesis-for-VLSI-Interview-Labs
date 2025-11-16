# RTL-Design-Synthesis-for-VLSI-Interview-Labs
<details>
  <summary> Setting up the environment on Codespace </summary>
  
- Codespace creation :
<p align="center">
<img width="496" height="342" alt="image" src="https://github.com/user-attachments/assets/ec58ede0-7248-4131-9db5-c20758739dc5" />
</p>

- Verifying yosys and iverilog installation :

 <p align="center"> <img width="851" height="597" alt="image" src="https://github.com/user-attachments/assets/d031bb5c-baaa-4daa-a8f7-95980c097737" />  <img width="1045" height="398" alt="image" src="https://github.com/user-attachments/assets/f7c54920-d249-4ef9-bcd2-1705073da1fb" />
  </p>

- Creating the port to provide a browser-based remote desktop (VNC) interface : 
 <p align="center"> <img width="1102" height="155" alt="image" src="https://github.com/user-attachments/assets/6786f19f-bdc8-4d5e-95fc-79e639122ca3" /></p>

- Opening the interface by selecting the vnc_lite.html : 

<p align="center"> <img width="593" height="335" alt="image" src="https://github.com/user-attachments/assets/f3c9e41a-57d4-47b9-92fc-b7100a14d0b9" /> </p>

- Verifying all the necessary tools by running the following commands in the terminal :
  ```
  cd /workspaces/vsd-rtl/
  ls -ltr
  gtkwave
  ```
 <p align="center"> <img width="1027" height="642" alt="image" src="https://github.com/user-attachments/assets/eecc4ffe-e136-4143-ab56-397b3ede8a05" /> </p>
 <p align="center"> <img width="1598" height="847" alt="image" src="https://github.com/user-attachments/assets/56d0e44a-6c96-4738-bdb9-95df5b42c8b9" /> </p>


</details>
<details>
  <summary>DAY-1</summary>
  
  ## Lecture-0: SKY130RTL D1SK1 L1 Introduction to iverilog design test bench
  
- **RTL design** simulator is a tool used for verifying the functionality of the design.
- **Design** is the actual module that is implemented, whereas the **testbench** is for verifying the design by considering various test cases.
- In this course, the simulator used is "**iverilog**" and the waveform viewer is the "**gtkwave**".
- Iverilog-based simulation flow :
  <p align="center"> <img width="838" height="417" alt="image" src="https://github.com/user-attachments/assets/8027cbb8-3c6c-4ebb-a015-a056333254cc" /> </p>

  ## Lecture-1: SKY130RTL D1SK2 L1 Lab1 introduction to lab
  Installation and cloning of all the necessary repositories required for running the labs. A folder named vsdrtlworkshop is created, and the sky130RTLSynthesisAndDesign repository is cloned into it.

  <p align="center"> <img width="1918" height="917" alt="image" src="https://github.com/user-attachments/assets/25a2f94e-867d-45f0-b1ca-9f98a97c0932" /> </p>

  ## Lecture-2: SKY130RTL D1SK2 L2 Lab2 Introduction iverilog gtkwave part1

  In this lab a good_mux.v is simulated and code is as follows :

  ```
  iverilog good_mux.v tb_good_mux.v
  ```

  An a.out file will be created

  ```
  ./a.out
  ```

  to view the waveforms on gtkwave :

  ```
  gtkwave tb_good_mux.vcd
  ```

  VCD stands for "**value change dump**"

  The results are as follows :

  <p align="center"><img width="1916" height="553" alt="image" src="https://github.com/user-attachments/assets/12897415-a163-4b8f-9648-24d24eeaf3a1" /></p>

  <p align="center"><img width="1917" height="918" alt="image" src="https://github.com/user-attachments/assets/a4e3ac22-84c1-4e68-b2ab-85ce11b5e765" /></p>

  ## Lecture-3: SKY130RTL D1SK2 L3 Lab2 Introduction iverilog gtkwave part2
  To open the code editor :
  ```
  gvim tb_good_mux.v -o good_mux.v
  ```
  <p align="center"><img width="1917" height="598" alt="image" src="https://github.com/user-attachments/assets/537d2470-1d46-4a71-ac06-3399eab31002" /></p>
  <p align="center"><img width="1917" height="910" alt="image" src="https://github.com/user-attachments/assets/df150ab4-2cb6-4fe4-8824-f7281cc2b598" /></p>

  ## Lecture-4:SKY130RTL D1SK3 L1 Introduction to yosys
  - **Synthesizer** is a tool used for converting the RTL code into the netlist.
  - The synthesiser tool used here is **"yosys**.

  <p align="center"><img width="1870" height="977" alt="image" src="https://github.com/user-attachments/assets/45c79362-888b-4d9c-a13a-205d85e860e7" /></p>
  <p align="center"><img width="1192" height="647" alt="image" src="https://github.com/user-attachments/assets/b00d5f5c-df00-435f-b29d-1339bcd3e470" /></p>

   ## Lecture-5: SKY130RTL D1SK3 L2 introduction to logic synthesis part1
  - RTL Design is a behavioural specification of the required design.
  -  RTL to gate-level synthesis is called as the netlist.
  -  .lib is the collection/bucket of all the logic cells. (AND, OR, NOT,
  <p align="center"><img width="895" height="607" alt="image" src="https://github.com/user-attachments/assets/20f16684-c757-4f85-aef9-1cbd9d5a2589" /></p>

  - To ensure that there are no hold issues in the circuit, we need cells that work slowly.

   ## Lecture-6: SKY130RTL D1SK3 L3 introduction to logic synthesis part2

  - **Setup time** is the time before the clock edge at which the data remains stable.
  - **Hold time** is the time after the clock edge at which the data remains stable.
  - Load in the digital circuits are nothing but the capacitances.
  - Faster charging/discharging with the lesser cell delay.
  - Wide transistors - more area and power but less delay, whereas narrow transistors- less area and less power but more delay.

  <p align="center"><img width="906" height="662" alt="image" src="https://github.com/user-attachments/assets/6e1fc570-12b9-4ddd-a696-27f3cbc48a31" /></p>

  ## Lecture-7: SKY130RTL D1SK4 L1 Lab3 Yosys 1 good mux Part1

  Commands to run :
  ```
  cd verilog_files
  ls
  ```
  ```
  yosys
  ```
  ```
  yosys> read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
  ```
  yosys > read_verilog good_mux.v
  ```
  ```
  yosys > synth -top good_mux
  ```
  <p align="center"><img width="1918" height="916" alt="image" src="https://github.com/user-attachments/assets/32fa8e4e-4561-48d2-b48c-7f2ccd9d8833" /></p>

  <p align="center"><img width="990" height="372" alt="image" src="https://github.com/user-attachments/assets/9d8bb860-b25c-4c49-a163-d1695669c188" /></p>

  ```
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
  The above code (RTL) will be realised in terms of the standard cells from the library.

  ```
  show
  ```
  The equivalent netlist will be opened.

  <p align="center"><img width="1911" height="622" alt="image" src="https://github.com/user-attachments/assets/0d093de1-8f57-4436-b713-953afaf0885c" /></p>

  <p align="center"><img width="1918" height="708" alt="image" src="https://github.com/user-attachments/assets/b3a2d1e3-bf0c-4e48-a41e-eb506039386b" /></p>
  
   ## Lecture-8: SKY130RTL D1SK4 L2 Lab3 Yosys 1 good mux Part2
   Here, the sky130_fd_sc_hd_mux2_1 standard cell library is used. with three input signals for i0, i1 and sel and one output signal y.
  <p align="center"><img width="888" height="341" alt="image" src="https://github.com/user-attachments/assets/81e5ca6a-4cf1-42ea-8fb5-9984e55efd4e" /></p>

   ## Lecture-9: SKY130RTL D1SK4 L2 Lab3 Yosys 1 good mux Part2

   To open the netlist file

   ```
   yosys > write_verilog good_mux_netlist.v
   ```

   ```
   yosys > !gvim good_mux_netlist.v
   ```

   <p align="center"><img width="1918" height="907" alt="image" src="https://github.com/user-attachments/assets/151a2ec8-2393-4a45-9a22-fdcd896f24b0" /></p>

   <p align="center"><img width="1918" height="946" alt="image" src="https://github.com/user-attachments/assets/e9cb9c74-2d0a-43b1-9efb-299a803e7cd9" /></p>

    ```
   yosys > write_verilog -noattr good_mux_netlist.v
   ```

   ```
   yosys > !gvim good_mux_netlist.v
   ```
    
   <p align="center"><img width="956" height="248" alt="image" src="https://github.com/user-attachments/assets/84bc9823-c701-4167-aeb3-8b4d3cd3fa9c" /></p>

   <p align="center"><img width="1918" height="945" alt="image" src="https://github.com/user-attachments/assets/ac49a929-6844-49c0-8c32-16549e3ca720" /></p>

  </details>
  
  <details>
    <summary>DAY-2</summary>
    
   ## Lecture-10: SKY130RTL D2SK1 L1 Lab4 Introduction to dot Lib part1

  ```
  gvim ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
  <p align="center"><img width="1913" height="936" alt="image" src="https://github.com/user-attachments/assets/0f4a0e6a-f729-41cb-9fc8-14939b7f5fd3" /></p>

  - sky130 is the library.
  - tt stands for typical process.
  - 025C is the temperature. (PVT - Process Variation Temperature -determines whether the silicon works faster or slower)
  - 1v80 indicates the voltage.

   ## Lecture-11: SKY130RTL D2SK1 L2 Lab4 Introduction to dot Lib part2

  - CMOS technology.
  - The delay model is a  look-up table.
  - capacitance, resistance, inductance.
  - unit of time is in **ns**.
  - .lib is the bucket of all the standard cells.
  - To enable line numbers, the command required is  :
    ```
    se nu
    ```
  - Consider the following example of **a2111o** :

    ```
    : sp ../lib/sky130_fd_sc_hd__a2111o.behavioral.v
    ```

    <p align="center"><img width="1918" height="952" alt="image" src="https://github.com/user-attachments/assets/bb9354c2-f405-4089-9a53-52774ae324bb" /></p>

    
  ## Lecture-12: SKY130RTL D2SK1 L3 Lab4 Introduction to dot Lib part3
  - To consider even a simpler example of  **and2_0**
    ```
    /cell .*and
    ```

    ```
    : sp ../lib/sky130_fd_sc_hd__and2.behavioral.v
    ```

    <p align="center"><img width="1917" height="936" alt="image" src="https://github.com/user-attachments/assets/023414ce-e31d-4d49-ab16-fd5fd9c56ca3" /></p>


    ## Lecture-13: SKY130RTL D2SK2 L1 Lab05 Hier synthesis flat synthesis part1

    The file used in this lab is the multiple_modules.v

    ```
    cd verilog_files
    gvim multiple_modules.v
    ```

    <p align="center"> <img width="1250" height="622" alt="image" src="https://github.com/user-attachments/assets/722ea4fd-37f5-4843-8ffe-dc6568daf95f" /> </p>

    to run yosys for the multiple_modules.v file

    ```
    cd verilog_files
    yosys
    ```

    ```
    yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    yosys > read_verilog multiple_modules.v
    yosys > synth -top multiple_modules
    yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    ```

    <p align="center"> <img width="783" height="815" alt="image" src="https://github.com/user-attachments/assets/ae77278f-ae0c-4d36-8ff4-0c9e4e21ad1d" /></p>
    <p align="center"><img width="1918" height="908" alt="image" src="https://github.com/user-attachments/assets/a0542d59-14ff-47af-b564-9dbdd26ef9c0" /></p>


    since there are multiple modules :
    ```
    show multiple_modules
    ```
    <p align="center"><img width="1918" height="948" alt="image" src="https://github.com/user-attachments/assets/f9ee3021-670a-4752-bdae-9e3adce6afaa" /></p>

    To write the same :

    ```
    yosys > write_verilog -noattr multiple_modules_hier.v
    yosys > !gvim multiple_modules_hier.v
    ```

    <p align="center"> <img width="1917" height="962" alt="image" src="https://github.com/user-attachments/assets/2559a35f-bb24-4241-a5cd-957710b21f45" /></p>

  - NAND is preferred because of the stacked nMOS (two nMOS in series) over NOR (having stacked pMOS, which is bad).
 
  ## Lecture-14: SKY130RTL D2SK2 L2 Lab05 Hier synthesis flat synthesis part2

  - To flatten out the netlist :
    ```
    yosys > flatten
    yosys > write_verilog -noattr multiple_modules.flat.v
    yosys > !gvim multiple_modules.flat.v
    ```
    <p align="center"> <img width="1917" height="972" alt="image" src="https://github.com/user-attachments/assets/d6919b7e-3be3-4443-998a-76a21dd61714" /></p>

    Netlist after flattening :

    <p align="center"><img width="1918" height="985" alt="image" src="https://github.com/user-attachments/assets/ee3cfbbd-c00a-46b7-9c19-e6aba47ea626" /></p>

    To perform sub-module synthesis :

    ```
    yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    yosys > read_verilog multiple_modules.v
    yosys > synth -top sub_module1
    yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    yosys > show
    ```
    <p align="center"><img width="1918" height="936" alt="image" src="https://github.com/user-attachments/assets/7b015ede-e5f9-47e1-b122-505ce9be042a" /></p>

    - Module level is preferred when we have multiple modules and want to incorporate the **divide and conquer** approach(hierarchical design)
   
    
    ## Lecture-15: SKY130RTL D2SK3 L1 Why Flops and Flop coding styles part1

    - A glitch is the momentary change of output.
    <p align="center"><img width="617" height="628" alt="image" src="https://github.com/user-attachments/assets/f60db8c0-5896-441b-a6c2-53f4a0d90638" /></p>

    - Why Flops? - To reduce glitches so that the output changes only on the edge of the clock. Control pins for resetting or presetting the flop are present.

    ## Lecture-16: SKY130RTL D2SK3 L2 Why Flops and Flop coding styles part2

    -  always block gets executed whenever there is a change in the clock or reset.
    -  **Asynchronous reset** is the reset that is independent of the clock signal.
      ```
    module dff_asyn_res(input clk,d,output q);
      always @(posedge clk or posedge rst)
      begin
        if(rst)
          q<=1'b0;
      //if(set)
          //q<=1'b1;
        else
          q<=d;
      end
    endmodule
      ```
    -  **Synchronous reset** is the reset that is dependent on the clock signal.
      ```
    module dff_syn_res(input clk,d,output q);
      always @(posedge clk)
      begin
        if(rst)
          q<=1'b0;
      //if(set)
          //q<=1'b1;
        else
          q<=d;
      end
    endmodule
      ```

    ## Lecture-17: SKY130RTL D2SK3 L3 Lab flop synthesis simulations part1

    To simulate all the designs :

    - Asynchronous reset : 
      <p align="center"><img width="1918" height="611" alt="image" src="https://github.com/user-attachments/assets/badd4da5-84cf-456a-b2da-76b57957fa47" /></p>
      <p align="center"> <img width="1916" height="946" alt="image" src="https://github.com/user-attachments/assets/7946720e-dcdb-46c2-bb2c-717d667c68ea" /></p>

    - Asynchronous set :

      <p align="center"><img width="1918" height="618" alt="image" src="https://github.com/user-attachments/assets/e4770bc7-a8f4-4ef9-93e0-8498c247cadb" /></p>
      <p align="center"><img width="1918" height="950" alt="image" src="https://github.com/user-attachments/assets/2ca82aa0-e542-4005-91af-b674d67ead88" /></p>

    - Synchronous reset : 
      <p align="center"><img width="1918" height="682" alt="image" src="https://github.com/user-attachments/assets/c9aa14fb-ea2c-42dc-8fc1-1705b275de1e" /></p>
      <p align="center"><img width="1918" height="947" alt="image" src="https://github.com/user-attachments/assets/5b9c5ed3-b3f5-403a-a1d7-8566cb99d057" /></p>


    ## Lecture-18: SKY130RTL D2SK3 L4 Lab flop synthesis simulations part2

    - Asynchronous reset
   
      ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog dff_asyncres.v
      yosys > synth -top dff_asyncres
      yosys > dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      ```
      <p align="center"><img width="858" height="333" alt="image" src="https://github.com/user-attachments/assets/8f17812d-ecbf-4d1f-ad71-e00732d78542" /></p>

      ```
      yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > show
      ```
      <p align="center"><img width="1918" height="988" alt="image" src="https://github.com/user-attachments/assets/802c5d19-b98c-4552-bb08-0310e8cd7711" /></p>

    - Asynchronous set
   
      ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog dff_async_set.v
      yosys > synth -top dff_async_set
      yosys > dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      ```
      <p align="center"><img width="792" height="297" alt="image" src="https://github.com/user-attachments/assets/9d1ac1bd-b126-4a1d-afab-9a640416cdfa" /></p>

      ```
      yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > show
      ```
      <p align="center"><img width="1917" height="962" alt="image" src="https://github.com/user-attachments/assets/61b4e3c3-0fbb-45a7-8b29-1092db5442b5" /></p>

    -  Synchronous set
   
      ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog dff_syncres.v
      yosys > synth -top dff_syncres
      yosys > dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      ```
      <p align="center"><img width="567" height="297" alt="image" src="https://github.com/user-attachments/assets/a9ed02bd-2999-4863-b615-64fbe65aa64b" /></p>

      ```
      yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > show
      ```
      <p align="center"><img width="1918" height="957" alt="image" src="https://github.com/user-attachments/assets/68599c2f-0ee4-4a00-8e4b-d245713d789f" /></p>


      ## Lecture-19: SKY130RTL D2SK3 L5 Interesting optimisations part1

      - Code Optimizations : Multiplying a number by 2 

        <p align="center"><img width="1266" height="717" alt="image" src="https://github.com/user-attachments/assets/85a5cf8c-15ea-4367-8bae-d8168db80403" /></p>

        output y[3:0] is simply {a,0} - multiplication by 2
        output y[4:0] is simply {a,0,0} -multipliation by 4

      - Multiplication by 2 :

    ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog mult_2.v
      yosys > synth -top mul2
    ```
    <p align="center"><img width="872" height="326" alt="image" src="https://github.com/user-attachments/assets/0c8dd276-a542-4604-87aa-c4c2314cbcc9" /></p>

    ```
      yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    ```

    <p align="center"><img width="867" height="187" alt="image" src="https://github.com/user-attachments/assets/ca3edc3f-85cc-4a43-8871-31818bc6e551" /></p>

    ```
    show
    ```

  <p align="center"><img width="1917" height="965" alt="image" src="https://github.com/user-attachments/assets/737d464a-bb1e-452a-a162-c437e6bcaf3d" /></p>
  
    - To view netlist :
      ```
      yosys > write_verilog -noattr mul2_net.v
      yosys > !gvim mul2_net.v
      ```
  <p align="center"><img width="1918" height="921" alt="image" src="https://github.com/user-attachments/assets/56e68b1a-55e9-428b-8740-89314de3cb7d" /></p>


    ## Lecture-20: SKY130RTL D2SK3 L6 Interesting optimisations part2

    - ax9 is nothing but ax[8+1] = ax8 +ax1 here a is a 3 bit number

      <p align="center"><img width="1255" height="708" alt="image" src="https://github.com/user-attachments/assets/52b32357-32bc-4149-91f4-e0fc41f694d7" /></p>

      ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog mult_8.v
      yosys > synth -top mult8
      ```
      <p align="center"><img width="785" height="318" alt="image" src="https://github.com/user-attachments/assets/e08d4562-d479-4c14-b216-b17da6339306" /></p>

    ```
      yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    ```

    <p align="center"><img width="747" height="147" alt="image" src="https://github.com/user-attachments/assets/52493937-4ce4-41f1-983d-297d843ebe43" /></p>

    ```
    show
    ```

    <p align="center"><img width="1918" height="998" alt="image" src="https://github.com/user-attachments/assets/039b4dda-b03f-431f-81b4-ef87c4abf5a5" /></p>

    - To view netlist :
      ```
      yosys > write_verilog -noattr mult8_net.v
      yosys > !gvim mult8_net.v
      ```

      <p align="center"><img width="1917" height="828" alt="image" src="https://github.com/user-attachments/assets/c1a72fc9-2180-4fba-9f4f-75d11b25c775" /></p>
  </details>

  <details>
  <summary>DAY-3</summary>

  ## Lecture-21: SKY130RTL D3SK1 L1 Introduction to optimisations part1

  - Boolean logic optimizations :

    <p align="center"><img width="1600" height="1467" alt="image" src="https://github.com/user-attachments/assets/b3309b4f-7fe7-445f-91cf-64487c17d474" /></p>

  ## Lecture-22: SKY130RTL D3SK1 L2 Introduction to optimisations part2

  - Sequential Logic Optimization : (Also called as sequential constant)

    <p align="center"><img width="1280" height="572" alt="image" src="https://github.com/user-attachments/assets/03236db9-4b37-467f-a846-0c151c5978fe" /></p>
    <p align="center"><img width="1440" height="1600" alt="image" src="https://github.com/user-attachments/assets/a014f4be-6a04-495a-9fa1-f90d7db4fe4b" /></p>

   ## Lecture-23: SKY130RTL D3SK1 L3 Introduction to optimisations part3

    <p align="center"><img width="1842" height="1028" alt="image" src="https://github.com/user-attachments/assets/78125807-b9b6-4f70-8807-9b419a289272" /></p>

    - This involves partitioning some portion of the logic by pushing it further.

    ## Lecture-24: SKY130RTL D3SK2 L1 Lab06 Combinational Logic Optimisations part1

    - Working on opt_check.v (and gate after optimisation)

      ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog opt_check.v
      yosys > synth -top opt_check
      ```

      <p align="center"><img width="617" height="375" alt="image" src="https://github.com/user-attachments/assets/a5e8392f-f77d-4f1c-9ceb-a229b53d706c" /></p>

      To optimise it :
      ```
      yosys > opt_clean -purge
      ```

       <p align="center"><img width="1180" height="338" alt="image" src="https://github.com/user-attachments/assets/b2bd053c-87ab-4255-bd87-d7e51e8c8743" /></p>

      ```
      yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      ```

      ```
      show
      ```
      <p align="center"><img width="1917" height="937" alt="image" src="https://github.com/user-attachments/assets/6c03a92b-892e-49ef-8146-f9a8760c6d2a" /></p>

     - Working on opt_check2.v (or gate after optimisation)

       <p align="center"><img width="1918" height="885" alt="image" src="https://github.com/user-attachments/assets/ea1f5821-c4c3-47b6-bd7c-c115f6bc0d63" /></p>


       ## Lecture-25: SKY130RTL D3SK2 L2 Lab06 Combinational Logic Optimisations part2

     - Working on opt_check3.v (3 input AND gate after optimisation)

      ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog opt_check3.v
      yosys > synth -top opt_check3
      ```
    <p align="center"><img width="645" height="363" alt="image" src="https://github.com/user-attachments/assets/c200e65b-127f-43d8-9757-a5a065935c9e" /></p>
    
     - To optimise it :
     
      ```
      yosys > opt_clean -purge
      ```

      ```
      yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      ```

      ```
      show
      ```

  <p align="center"><img width="1918" height="927" alt="image" src="https://github.com/user-attachments/assets/e235a70a-7817-44c3-9818-c6855fd0e3de" /></p>

    - Working on opt_check4.v (XNOR of A and C)

     <p align="center"> <img width="625" height="376" alt="image" src="https://github.com/user-attachments/assets/3c2362cd-0e8d-48f7-a600-13875262f9f4" /></p>

     <p align="center"><img width="1918" height="953" alt="image" src="https://github.com/user-attachments/assets/8bb10e48-a59b-4d88-85cd-d8af6e91ee7c" /></p>

    - Working on multiple_modules_opt.v (a21o gate)
 
      ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog multiple_modules_opt.v
      yosys > synth -top multiple_modules_opt
      ```

      <p align="center"><img width="807" height="793" alt="image" src="https://github.com/user-attachments/assets/9c9d2aec-3ea4-4b56-90e1-3ffeb6bd954f" /></p>
      
      ```
      yosys > abc -liberty ..lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > show multiple_module_opt
      ```
      
      <p align="center"><img width="1917" height="942" alt="image" src="https://github.com/user-attachments/assets/099dd337-1a01-4288-96fc-a3eb10bdeae7" /></p>

      ```
      yosys > write_verilog -noattr multiple_module_opt_hier.v
      yosys > !gvim multiple_module_opt_hier.v
      ```
      <p align="center"><img width="1912" height="885" alt="image" src="https://github.com/user-attachments/assets/e14dc756-85d3-440c-9c96-c6655e072b8e" /></p>

      ```
      yosys > flatten
      yosys > write_verilog -noattr multiple_module_opt_flat.v
      yosys > !gvim multiplr_module_opt_flat.v
      ```

      <p align="center"><img width="688" height="366" alt="image" src="https://github.com/user-attachments/assets/13b61cd0-eb62-44f6-8306-8408c5315f19" /></p>

      <p align="center"><img width="1917" height="926" alt="image" src="https://github.com/user-attachments/assets/4aa7188b-4bb1-4220-8ea0-0c3689cdfcfb" /></p>

      ```
      yosys > opt_clean -purge
      yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > show
      ```

      <p align="center"><img width="1918" height="922" alt="image" src="https://github.com/user-attachments/assets/aece825c-26ab-41fb-88db-b28f8333eb21" /></p>

    - Working on multiple_modules_opt2.v ( gate)

        <p align="center"><img width="762" height="773" alt="image" src="https://github.com/user-attachments/assets/db5bbee7-1487-4bfb-995a-8bb6c778f064" /></p>

        <p align="center"><img width="1918" height="957" alt="image" src="https://github.com/user-attachments/assets/136b8f46-9e41-47d0-aa42-1a438d0cff4c" /></p>

        <p align="center"><img width="1918" height="953" alt="image" src="https://github.com/user-attachments/assets/64f46535-c982-4460-ac09-c844423048d2" /></p>

        <p align="center"><img width="1907" height="953" alt="image" src="https://github.com/user-attachments/assets/86ec2cae-139e-4599-9ff5-bca236cd96dd" /></p>

        <p align="center"><img width="1915" height="897" alt="image" src="https://github.com/user-attachments/assets/435ac7ed-2405-4c03-85ba-ec94d53a5b6c" /></p>

      ## Lecture-26: SKY130RTL D3SK3 L1 Lab07 Sequential Logic Optimisations part1

      - Working on dff_const1.v :

        ```
        iverilog tb_dfF_const1.v dff_const1.v
        ./a.out
        gtkwave tb_dff_const1.vcd
        ```
        <p align="center"><img width="1915" height="933" alt="image" src="https://github.com/user-attachments/assets/f5cae4d4-1270-4116-8479-23f0dbba789b" /></p>
 
      ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog dff_const1.v
      yosys > synth -top dff_const1
      ```
      <p align="center"><img width="598" height="248" alt="image" src="https://github.com/user-attachments/assets/1bd9a9e6-0ead-4e22-ae90-2da85d13733b" /></p>
 
      ```
      yosys > dfflibmap -liberty ../lib/sky130-fd_sc_hd__tt_025C_1v80.lib
      ```
 
      <p align="center"><img width="1027" height="612" alt="image" src="https://github.com/user-attachments/assets/6050bcd7-42dc-4d9e-8393-b60478d0c873" /></p>
 
      ```
      show
      ```
      <p align="center"><img width="1916" height="946" alt="image" src="https://github.com/user-attachments/assets/8d4359de-7777-467f-b05c-75a8188f0df0" /></p>
 

      ## Lecture-27: SKY130RTL D3SK3 L2 Lab07 Sequential Logic Optimisations part2

      - Working on dff_const2.v :

        ```
        iverilog tb_dfF_const2.v dff_const2.v
        ./a.out
        gtkwave tb_dff_const2.vcd
        ```
        <p align="center"><img width="1916" height="917" alt="image" src="https://github.com/user-attachments/assets/74775511-b0d3-406c-a7af-d235bfc1d06d" /></p>

      ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog dff_const2.v
      yosys > synth -top dff_const2
      ```
      <p align="center"><img width="583" height="256" alt="image" src="https://github.com/user-attachments/assets/7b4cbef5-ca34-42f4-84d2-b59ac50ba68a" /></p>
 
      Now, since no flop is required
 
      ```
      yosys >abc -liberty ../lib/sky130-fd_sc_hd__tt_025C_1v80.lib
      yosys > show
      ```
 
      <p align="center"><img width="1916" height="960" alt="image" src="https://github.com/user-attachments/assets/caa7b632-57c1-4e60-b8f7-2bb16cfb2abd" /></p>

      ## Lecture-28: SKY130RTL D3SK3 L3 Lab07 Sequential Logic Optimisations part3

     - Working on dff_const3.v

       ```
        iverilog tb_dfF_const3.v dff_const3.v
        ./a.out
        gtkwave tb_dff_const3.vcd
       ```

        <p align="center"><img width="1917" height="918" alt="image" src="https://github.com/user-attachments/assets/4d355a59-b531-4e1a-b62c-392e9bd90801" /></p>

     ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog dff_const3.v
      yosys > synth -top dff_const3
     ```
  <p align="center"><img width="557" height="286" alt="image" src="https://github.com/user-attachments/assets/55904c48-aec4-477e-ac3f-5f57e8c2efe9" /></p>

   ```
      yosys > dfflibmap -liberty ../lib/sky130-fd_sc_hd__tt_025C_1v80.lib
      yosys > abc -liberty ../lib/sky130-fd_sc_hd__tt_025C_1v80.lib
      yosys > show
   ```

  <p align="center"><img width="1913" height="927" alt="image" src="https://github.com/user-attachments/assets/4a6cf95f-8c34-4f46-9ad5-277e00b6c037" /></p>

  - Working on dff_const4.v

    ```
        iverilog tb_dfF_const4.v dff_const4.v
        ./a.out
        gtkwave tb_dff_const4.vcd
     ```

    <p align="center"><img width="1918" height="927" alt="image" src="https://github.com/user-attachments/assets/8464fb60-c830-4db7-8571-1cf57541445e" /></p>

      ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog dff_const4.v
      yosys > synth -top dff_const4
      ```
  <p align="center"><img width="506" height="246" alt="image" src="https://github.com/user-attachments/assets/289ad699-ea58-4af6-a9a4-d1dc4ed2d7df" /></p>

  Since no flop is required : 

   ```
      yosys > abc -liberty ../lib/sky130-fd_sc_hd__tt_025C_1v80.lib
      yosys > show
   ```
  <p align="center"><img width="1918" height="928" alt="image" src="https://github.com/user-attachments/assets/d9647f98-b097-4a17-bb35-ac0cd658e45a" /></p>

  - Working on dff_const3.v

     ```
        iverilog tb_dfF_const5.v dff_const5.v
        ./a.out
        gtkwave tb_dff_const5.vcd
      ```

    <p align="center"><img width="1916" height="922" alt="image" src="https://github.com/user-attachments/assets/b2945909-c835-43bf-aded-b063c150f3dc" /></p>

    ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog dff_const3.v
      yosys > synth -top dff_const3
    ```
  <p align="center"><img width="558" height="272" alt="image" src="https://github.com/user-attachments/assets/bc417747-3093-4351-ab16-e1a588e717b1" /></p>

  ```
      yosys > dfflibmap -liberty ../lib/sky130-fd_sc_hd__tt_025C_1v80.lib
      yosys > abc -liberty ../lib/sky130-fd_sc_hd__tt_025C_1v80.lib
      yosys > show
   ```
  <p align="center"><img width="1918" height="922" alt="image" src="https://github.com/user-attachments/assets/060f8ddd-57dc-40e0-a148-f05d4e1a242e" /></p>

    ## Lecture-29: SKY130RTL D3SK4 L1 Seq optimisation unused outputs part1

    - Working on 3-bit up counter (counter_opt.v with q=count[0])

      ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog counter_opt.v
      yosys > synth -top counter_opt
      ```
      <p align="center"><img width="417" height="286" alt="image" src="https://github.com/user-attachments/assets/f2bbd07b-3400-4cc0-87c6-461a9159a565" /></p>

      ```
      yosys > dfflibmap -liberty ../lib/sky130-fd_sc_hd__tt_025C_1v80.lib
      yosys > abc -liberty ../lib/sky130-fd_sc_hd__tt_025C_1v80.lib
      yosys > show
      ```
      <p align="center"><img width="1918" height="928" alt="image" src="https://github.com/user-attachments/assets/ab721e86-e63d-42a7-93b6-75648d883aea" /></p>

      This netlist is nothing but same as circuit shown in below image :
      <p align="center"><img width="1539" height="1600" alt="image" src="https://github.com/user-attachments/assets/0e8cba0a-e7a6-4f90-bd11-deefed47449d" /></p>


      ## Lecture-30: SKY130RTL D3SK4 L2 Seq optimisation unused outputs part2

  - Working on 3-bit up counter (counter_opt2.v)
     
     ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog counter_opt2.v
      yosys > synth -top counter_opt2
     ```
   <p align="center"><img width="537" height="350" alt="image" src="https://github.com/user-attachments/assets/5ce93b07-1bd6-433c-a3f3-bb2ecf678760" /></p>

   ```
      yosys > dfflibmap -liberty ../lib/sky130-fd_sc_hd__tt_025C_1v80.lib
      yosys > abc -liberty ../lib/sky130-fd_sc_hd__tt_025C_1v80.lib
      yosys > show
   ```
  <p align="center"><img width="1918" height="918" alt="image" src="https://github.com/user-attachments/assets/5869d181-11af-4a1e-9d8b-300ac1d6ccf0" /></p>

  <p align="center"><img width="1222" height="512" alt="image" src="https://github.com/user-attachments/assets/f210d35e-6572-429a-bd99-a36c2f64ab23" /></p>
  
  </details>

  <details>
    <summary>DAY-4</summary>

  ## Lecture-31: SKY130RTL D4SK1 L1 GLSConceptsAndFlowUsingIverilog

    - **"GLS"** stands for Gate Level Simulation.
    - GLS is nothing but running the netlist with testbench as netlist is same as the RTL code.

  <p align="center"><img width="1207" height="635" alt="image" src="https://github.com/user-attachments/assets/c2163aff-bc27-467f-85d4-30edd1d82e16" /></p>

    - Gate level verilog models contain the information about the behavior of the standard cells.
    - If Gate level verilog models are timing aware then they can be used for timing validation as well.
 
  ## Lecture-32: SKY130RTL D4SK1 L2 SynthesisSimulationMismatch

  - Synthesis and Simulation mismatches can occur due to :
    - Missing sensitivity list.
    - Blocking vs non blocking assignments.
    - Non standard verilog coding.

  - Missing Sensitivity list :

     <p align="center"><img width="1247" height="692" alt="image" src="https://github.com/user-attachments/assets/4ee18fef-3140-4421-b0fc-1636cc7c2ea7" /></p>

  ## Lecture-33: SKY130RTL D4SK1 L3 BlockingAndNonBlockingStatementsInVerilog

  - Blocking vs Non Blocking Assignments:
    - **Blocking assignment (=)**: evaluates sequentially line by line.
    - **Non Blocking assignment (<=)**: evaluates parallely.

    <p align="center"><img width="1212" height="662" alt="image" src="https://github.com/user-attachments/assets/7963bbd0-0585-4bf5-8291-f7d58c8b4462" /></p>

    
  ## Lecture-34: SKY130RTL D4SK1 L4 CaveatsWithBlockingStatements
  
  - Verilog code for shift register using blocking statements :
    ```
    module shift(input clk,d,rst,output q0,q);
    always @(posedge clk or posedge rst)
      begin
        if(rst)
          begin
              q0=1'b0;
              q=1'b0;
          end
        else
          begin
             q=q0;
             q0=d;
          end
      end
    endmodule
    ```
  - Verilog code for shift register using non-blocking statements :
    ```
    module shift(input clk,d,rst,output reg q0,q);
    always @(posedge clk or posedge rst)
      begin
        if(rst)
          begin
              q0<=1'b0;
              q<=1'b0;
          end
        else
          begin
             q0<=d;
             q<=q0;
          end
      end
    endmodule
    ```
  - Suppose if the following code is written assuming it will synthesize a shift register:
    ```
    module shift(input clk,d,rst,output q0,q);
    always @(posedge clk or posedge rst)
      begin
        if(rst)
          begin
              q0=1'b0;
              q=1'b0;
          end
        else
          begin
             q0=d;
             q=q0;
          end
      end
    endmodule
    ```

  - q0 already has the value of d , hence q will simply follow d and only one flip flop will be synthesized as we have used the blocking assignment.So this is the blocking vs non blocking mismatch.
  - Hence , we must use non blocking statements for modelling sequential circuits.

  ## Lecture-35: SKY130RTL D4SK2 L1 Lab GLS Synth Sim Mismatch part1

  - Wokring on ternary_operator_mux.v
     - 2x1 MUX using trernary operator :
       ```
       module mux21(input i0,i1,s,output out);
       assign out = s?i1:i0;
       endmodule
       ```

       ```
       iverilog tb_ternary_operator_mux.v ternary_operator_mux.v
       ./a.out
       gtkwave tb_ternary_operator_mux.vcd
       ```
       <p align="center"><img width="1918" height="930" alt="image" src="https://github.com/user-attachments/assets/d6e76f3f-05e0-45ae-8e32-53b88364792f" /></p>

       ```
       yosys
       yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
       yosys > read_verilog ternary_operator_mux.v
       yosys > synth -top ternary_operator_mux
       ```

       <p align="center"><img width="553" height="277" alt="image" src="https://github.com/user-attachments/assets/93469649-4006-46f3-9ee1-769b9bb57433" /></p>

       ```
       yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
       yosys > show
       ```
       <p align="center"><img width="1917" height="941" alt="image" src="https://github.com/user-attachments/assets/d35dc1c6-1056-4337-85b0-cf4588b2ad1a" /></p>

       ```
       yosys > write_verilog -noattr ternary_operator_mux_net.v
       yosys > !gvim ternary_operator_mux_net.v
       ```
       
       <p align="center"><img width="1917" height="913" alt="image" src="https://github.com/user-attachments/assets/e4e5738d-f08e-4b47-89a8-2afe1685c43d" /></p>

       Now to do GLS :

       ```
       iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v ternary_operator_mux_net.v tb_ternary_operator_mux.v
       ./a.out
       gtkwave tb_ternary_operator_mux.vcd
       ```

       <p align="center"><img width="1918" height="917" alt="image" src="https://github.com/user-attachments/assets/a51df72f-8101-483c-84f1-fb7996298917" /></p>

       The red circle in the above image indicates that the GLS has been performed.

    ## Lecture-36: SKY130RTL D4SK2 L2 Lab GLS Synth Sim Mismatch part2

    - Working on bad_mux.v

       ```
       iverilog tb_bad_mux.v bad_mux.v
       ./a.out
       gtkwave tb_bad_mux.vcd
       ```
       <p align="center"><img width="1918" height="918" alt="image" src="https://github.com/user-attachments/assets/ceea8d43-309c-4fd9-aeaa-7fda9bd0dbdf" /></p>

       ```
       yosys
       yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
       yosys > read_verilog bad_mux.v
       yosys > synth -top bad_mux
       ```

       <p align="center"><img width="530" height="278" alt="image" src="https://github.com/user-attachments/assets/f5839aeb-6c04-42c4-8f9c-6c538b8c551f" /></p>

       ```
       yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
       yosys > write_verilog -noattr bad_mux_net.v
       ```

       ```
       iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v bad_mux_net.v tb_bad_mux.v
       ./a.out
       gtkwave tb_bad_mux.vcd
       ```
       
       <p align="center"><img width="1918" height="925" alt="image" src="https://github.com/user-attachments/assets/a9057227-060f-45be-a0fc-a33d970b08dc" /></p>

    ## Lecture-37: SKY130RTL D4SK3 L1 Lab Synth sim mismatch blocking statement part1

    - Working with blocking_caveat.v :
      ```
      iverilog blocking_caveat.v tb_blocking_caveat.v
      ./a.out
      gtkwave tb_blocking_caveat.vcd
      ```

      <p align="center"><img width="1917" height="925" alt="image" src="https://github.com/user-attachments/assets/119d18f9-5ab3-4573-83fc-96c50296df5f" /></p>

    ## Lecture-38: SKY130RTL D4SK3 L2 Lab Synth sim mismatch blocking statement part2

      ```
      yosys
      yosys > read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > read_verilog blocking_caveat.v
      yosys > synth -top blocking_caveat
      ```

      <p align="center"><img width="520" height="296" alt="image" src="https://github.com/user-attachments/assets/20596c6d-0372-43c6-9312-548c29687d07" /></p>

      ```
      yosys > abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
      yosys > write_verilog -noattr blocking_caveat.v
      yosys > show
      ```

      <p align="center"><img width="1917" height="927" alt="image" src="https://github.com/user-attachments/assets/7d0e2bcf-4928-45b5-9c0a-6f4c1d8432da" /></p>

       Now to do GLS :

       ```
       iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v blocking_caveat_net.v tb_blocking_caveat.v
       ./a.out
       gtkwave tb_blocking_caveat.vcd
       ```

       <p align="center"><img width="1918" height="910" alt="image" src="https://github.com/user-attachments/assets/0be077ab-4bc1-4330-bae4-002c6c024a1a" /></p>

      

      
      
      

      

       


       


        
       

       



       
   
    

    
    


    
    
















  </details>

   
    
    
  


  

    
