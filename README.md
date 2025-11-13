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

    
