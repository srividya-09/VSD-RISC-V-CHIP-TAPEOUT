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

## D Flip-Flop with Synchronous Reset
<img width="2492" height="1376" alt="image" src="https://github.com/user-attachments/assets/d3a31f67-3688-4879-80b7-05b4fc49330d" />
<img width="2464" height="188" alt="image" src="https://github.com/user-attachments/assets/ea6ea48e-369d-4ebc-8926-84f5f8aa1e45" />
<img width="2746" height="1512" alt="image" src="https://github.com/user-attachments/assets/72e18fa2-907d-42e3-ad9d-4d9eb72f611a" />

## D Flip-Flop with Both Asynchronous and Synchronous Reset
<img width="2748" height="1494" alt="image" src="https://github.com/user-attachments/assets/31bf4b69-509c-4bc7-bf17-0412c1958cac" />

## Synthesis of D Flip-Flop with Asynchronous set
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog dff_async_set.v
synth -top dff_async_set
dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
<img width="2724" height="1298" alt="image" src="https://github.com/user-attachments/assets/17000e4b-840a-494a-a21d-4b4e14c5e149" />
<img width="2730" height="1500" alt="image" src="https://github.com/user-attachments/assets/32cef819-a7f0-45b9-ac83-cf31c03f8695" />

## Synthesis of D Flip-Flop with Asynchronous Reset
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog dff_asyncres.v 
synth -top dff_asyncres
dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show

<img width="2744" height="1122" alt="image" src="https://github.com/user-attachments/assets/0a855fb0-b825-4203-8766-ec208e9ff9f6" />
<img width="2752" height="1506" alt="image" src="https://github.com/user-attachments/assets/addcf5ee-e114-4aa5-9ce6-f89f13dad240" />

## Synthesis of D Flip-Flop with Synchronous Reset
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog dff_syncres.v 
synth -top dff_syncres
dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show

<img width="2376" height="730" alt="image" src="https://github.com/user-attachments/assets/fb10646c-3053-4d94-8e4d-3c13863b6ea4" />
<img width="2750" height="1332" alt="image" src="https://github.com/user-attachments/assets/8424dfef-6f67-4807-88e3-7908950be0f5" />

## Synthesis of D Flip-Flop with Both Asynchronous and Synchronous Reset
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog dff_asyncres_syncres.v
synth -top dff_asyncres_syncres
dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show

<img width="2752" height="914" alt="image" src="https://github.com/user-attachments/assets/60bf76e9-24c0-4110-93c4-a2edeec08f36" />
<img width="2754" height="1238" alt="image" src="https://github.com/user-attachments/assets/7ce04472-8024-4010-becb-b42a15ce66d1" />

## Interesting optimisations
### part1
<img width="2678" height="1494" alt="image" src="https://github.com/user-attachments/assets/af57d94e-bdc8-4fcf-9c65-e8583e1b9efa" />
image need to be added 
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog mult_2.v
synth -top mul2
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib # no need to do this step becoz no cells are used #
show
write_verilog -noattr mult2_net.v

<img width="2540" height="1196" alt="image" src="https://github.com/user-attachments/assets/d9375542-ea7b-4751-9ecb-c8c3ecff2a85" />
<img width="2764" height="1426" alt="image" src="https://github.com/user-attachments/assets/8dea3781-e3ef-4990-a600-cd1c0cc9c85f" />
<img width="2736" height="1500" alt="image" src="https://github.com/user-attachments/assets/153a439e-974b-4ff5-b9d1-76866d51cf82" />

### part 2
<img width="2224" height="1310" alt="image" src="https://github.com/user-attachments/assets/1044a44d-4d2c-4365-a33f-f5c8b13297d0" />
yosy
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog mult_8.v
synth -top mult8
show
write_verilog -noattr mult8_net.v

<img width="2090" height="1142" alt="image" src="https://github.com/user-attachments/assets/90a17c25-3b77-410f-9557-0deea4e5c2e1" />
<img width="2128" height="604" alt="image" src="https://github.com/user-attachments/assets/96014843-4d85-4b99-9bbe-2af4b37dda03" />
<img width="2756" height="1262" alt="image" src="https://github.com/user-attachments/assets/930d586c-2d1b-4a93-8f47-758eade10091" />

Day3 
### combinational logic optimizations
### lab1
<img width="2210" height="656" alt="image" src="https://github.com/user-attachments/assets/289b2365-7107-4f5f-bebe-bacffc43582e" />
image need to added
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog opt_check.v 
synth -top opt_check
opt_clean -purge # Removes unused or redundant logic #
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show

<img width="2756" height="1074" alt="image" src="https://github.com/user-attachments/assets/ec67d4af-bb1a-4f14-b22e-1c02c75fdf6d" />
<img width="2730" height="1382" alt="image" src="https://github.com/user-attachments/assets/9fcdfc7c-95c4-4d82-b93f-9b7a249688fa" />

### lab2 
<img width="2202" height="550" alt="image" src="https://github.com/user-attachments/assets/50685d99-0e54-4106-ac1a-79411b6b595e" />

yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog opt_check2.v 
synth -top opt_check2
opt_clean -purge
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show

<img width="2662" height="1280" alt="image" src="https://github.com/user-attachments/assets/3661d56a-46d9-491e-a28e-0171324f135e" />
<img width="2752" height="1294" alt="image" src="https://github.com/user-attachments/assets/a7b03078-007e-483e-a4bd-9b85ab7a1348" />

### lab3 
<img width="2214" height="532" alt="image" src="https://github.com/user-attachments/assets/c013b1f6-2915-483d-b5d3-96be0f714c92" />
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog opt_check3.v 
synth -top opt_check3
opt_clean -purge
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
<img width="2740" height="1358" alt="image" src="https://github.com/user-attachments/assets/9a318afb-aa13-49f1-ae6f-e39036105831" />
<img width="2198" height="482" alt="image" src="https://github.com/user-attachments/assets/9d66726a-27b6-4410-9d51-207d58594f29" />

### lab4 
<img width="2198" height="482" alt="image" src="https://github.com/user-attachments/assets/38116ff5-1b3d-415d-a4b4-de941afe5379" />

yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog opt_check4.v 
synth -top opt_check4
opt_clean -purge
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show

<img width="2746" height="982" alt="image" src="https://github.com/user-attachments/assets/42015753-5225-458b-9b27-2edc48664ddb" />
<img width="2742" height="1414" alt="image" src="https://github.com/user-attachments/assets/30726c44-cfff-4e9e-8e3f-c056994fd6d5" />

### lab5 multiple_module_opt1
<img width="2214" height="960" alt="image" src="https://github.com/user-attachments/assets/6d92420f-12a1-49ef-9f0c-fba95ae05b42" />
### Phase 1: Flatten the hierarchical RTL design
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog multiple_module_opt.v
synth -top multiple_module_opt
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
flatten
write_verilog -noattr multiple_module_opt_flat.v

<img width="2686" height="1382" alt="image" src="https://github.com/user-attachments/assets/5b59ad61-a372-4114-96c2-c05545a726ac" />


### Phase 2: Optimize the flattened netlist
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog multiple_module_opt_flat.v
synth -top multiple_module_opt
opt_clean -purge
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show

<img width="2734" height="1376" alt="image" src="https://github.com/user-attachments/assets/ae5c84f9-36e8-4b99-ac6c-0a941c4a3e61" />

### lab6 - multiple_module_opt2
<img width="2226" height="1074" alt="image" src="https://github.com/user-attachments/assets/2f5cf546-68a5-4f6a-936b-e330d58c3a36" />
### Phase 1: Flatten the hierarchical RTL design
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog multiple_module_opt2.v
synth -top multiple_module_opt2
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
flatten
write_verilog -noattr multiple_module_opt2_flat.v
<img width="2730" height="1384" alt="image" src="https://github.com/user-attachments/assets/c51c658f-25e8-446a-89c8-cd0d3e693da6" />

### Phase 2: Optimize the flattened netlist
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog multiple_module_opt2_flat.v
synth -top multiple_module_opt2
opt_clean -purge
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
<img width="2754" height="1464" alt="image" src="https://github.com/user-attachments/assets/70f38f0a-6ccc-48fd-bf48-2c528be4777a" />

### Sequential Logic Optimization examples
### lab1
<img width="2228" height="782" alt="image" src="https://github.com/user-attachments/assets/db5617d0-5ac4-405f-8eaa-fe160344a309" />
<img width="2360" height="306" alt="image" src="https://github.com/user-attachments/assets/948f2975-fa99-404b-87c2-e46cb3b97181" />
<img width="2744" height="1028" alt="image" src="https://github.com/user-attachments/assets/8a1b0012-ad1a-4aea-a837-506835c79307" />

yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog dff_const1.v
synth -top dff_const1
dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
<img width="2752" height="1364" alt="image" src="https://github.com/user-attachments/assets/68fc206a-b1d2-4f3a-b9f9-d6e1cdcc215d" />

### lab2
<img width="2206" height="688" alt="image" src="https://github.com/user-attachments/assets/e486c428-2f4f-41d4-a0aa-9a26b35adc1f" />
<img width="2364" height="262" alt="image" src="https://github.com/user-attachments/assets/2daa80a8-641f-4d7e-bc2a-428e207765ab" />
<img width="2754" height="1034" alt="image" src="https://github.com/user-attachments/assets/4ccaef07-28c7-481c-a8b1-093611da3f6f" />

yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog dff_const2.v
synth -top dff_const2
dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
<img width="2740" height="1270" alt="image" src="https://github.com/user-attachments/assets/d256b8d4-ab0c-4a63-805f-8fd64e8e422d" />

### lab3 
<img width="2204" height="904" alt="image" src="https://github.com/user-attachments/assets/cbc81212-a589-49f2-b091-74063bde18a6" />
<img width="2362" height="222" alt="image" src="https://github.com/user-attachments/assets/33e81810-1c87-478a-b73f-ef08197ab3ee" />
<img width="2756" height="984" alt="image" src="https://github.com/user-attachments/assets/49e61cc7-270f-418f-afde-b9340184c77f" />

yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog dff_const3.v
synth -top dff_const3
dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
<img width="2756" height="1360" alt="image" src="https://github.com/user-attachments/assets/91a75c69-35ed-439b-b6c5-f341f43e0769" />




























































