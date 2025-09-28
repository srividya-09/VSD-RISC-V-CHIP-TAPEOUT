## Labs

<img width="2306" height="650" alt="image" src="https://github.com/user-attachments/assets/aa6647e9-68bf-4773-9cea-db9e82c60096" />
** Lab1
## Good_mux

<img width="2580" height="1522" alt="image" src="https://github.com/user-attachments/assets/c021bd56-a47b-4317-98a7-b882dd0e3710" />

<img width="2706" height="1464" alt="image" src="https://github.com/user-attachments/assets/5a117007-c02c-449b-b56b-e00e848cba53" />

## Yosys Synthesis Steps for good_mux

<img width="2544" height="1372" alt="image" src="https://github.com/user-attachments/assets/2551f1a4-c8ca-4576-bb63-7f6d74969ae6" />
<img width="2739" height="902" alt="Screenshot 2025-09-28 111136" src="https://github.com/user-attachments/assets/21c41106-bc19-4731-b6a6-5448849fb733" />
<img width="2759" height="578" alt="Screenshot 2025-09-28 111102" src="https://github.com/user-attachments/assets/3abde22e-0870-4db5-979b-0fa4a70b02a1" />
<img width="2072" height="1457" alt="Screenshot 2025-09-28 110932" src="https://github.com/user-attachments/assets/5faf45a7-1f02-4743-a259-edeb1e761b0e" />
<img width="2731" height="1532" alt="Screenshot 2025-09-28 111409" src="https://github.com/user-attachments/assets/20298e45-274b-479d-a550-0b00f0bafcb0" />




##Liberty format

<img width="2744" height="1546" alt="Screenshot 2025-09-28 111753" src="https://github.com/user-attachments/assets/ce01353b-b580-402e-97c2-54d4b956be01" />
<img width="2750" height="1512" alt="Screenshot 2025-09-28 111857" src="https://github.com/user-attachments/assets/28e965bd-b50a-4a7a-8e1b-b83d24bf4692" />
<img width="2758" height="1495" alt="Screenshot 2025-09-28 111941" src="https://github.com/user-attachments/assets/26cbadd4-ca4c-41ac-a7ea-3cca77fb8b6f" />
<img width="2747" height="1507" alt="Screenshot 2025-09-28 114535" src="https://github.com/user-attachments/assets/69fc86c0-c353-4e0a-b469-1912ba62be86" />

## Hierarchical vs Flat Synthesis (Yosys)

<img width="2737" height="1513" alt="Screenshot 2025-09-28 115313" src="https://github.com/user-attachments/assets/f7e2ef04-6429-4267-b53c-f1234c9f7271" />

### Hierarchical Flow:

yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog multiple_modules.v
synth -top multiple_modules
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show multiple_modules
write_verilog -noattr multiple_modules_netlist.v

<img width="2716" height="1524" alt="Screenshot 2025-09-28 115617" src="https://github.com/user-attachments/assets/b48912b8-9a60-4d56-bd44-bb9db7a239f5" />
<img width="2765" height="1511" alt="Screenshot 2025-09-28 115821" src="https://github.com/user-attachments/assets/49c4513a-0a80-4d3c-ad66-053b0e7e4da8" />
<img width="2739" height="1510" alt="Screenshot 2025-09-28 120250" src="https://github.com/user-attachments/assets/4e45a992-1343-4a30-b0f3-c25ec0e665e5" />

### Flattened Flow:
A flat design is a representation where all hierarchical module structures are collapsed into a single level, eliminating submodules and integrating their logic directly into the top-level module.

No submodules are preserved.

flatten
write_verilog -noattr multiple_modules_flat.v
<img width="2408" height="706" alt="image" src="https://github.com/user-attachments/assets/1b568e1e-c0ea-4e70-85c0-895d4422e9b6" />

<img width="2722" height="1527" alt="Screenshot 2025-09-28 123014" src="https://github.com/user-attachments/assets/e57141bb-26dd-4ded-a221-0238b434c9f3" />
<img width="2746" height="1526" alt="image" src="https://github.com/user-attachments/assets/be0d4c2a-07ea-4c5a-83e3-1097f2f94a1b" />

## Why Do We Use Flops? (To Avoid Glitches)
<img width="2742" height="1506" alt="image" src="https://github.com/user-attachments/assets/5ded65ff-3b9c-47d4-82bf-3948b47ca3c3" />

## D Flip-Flop with Asynchronous Reset
<img width="2744" height="1496" alt="image" src="https://github.com/user-attachments/assets/5b8dd36b-7291-4b41-8c9b-356a2e8830cb" />
<img width="2746" height="1544" alt="image" src="https://github.com/user-attachments/assets/62312731-ab2f-454c-99ce-475d15573f03" />















