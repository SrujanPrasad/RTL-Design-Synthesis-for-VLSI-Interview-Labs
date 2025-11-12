# RTL-Design-Synthesis-for-VLSI-Interview-Labs

## 12/11/2025
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
  <summary>Lecture-1: SKY130RTL D1SK1 L1 Introduction to iverilog design test bench</summary>
  
- **RTL design** simulator is a tool used for verifying the functionality of the design.
- **Design** is the actual module that is implemented, whereas the **testbench** is for verifying the design by considering various test cases.
- In this course, the simulator used is "**iverilog**".
- Iverilog-based simulation flow :
  <p align="center"> <img width="838" height="417" alt="image" src="https://github.com/user-attachments/assets/8027cbb8-3c6c-4ebb-a015-a056333254cc" /> </p>

  
