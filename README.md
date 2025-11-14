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


    

    

    


















  </details>


   
    
    
  


  

    
