Snow White Concurrency Simulation

- Name: Robert Bennethum IV
- Email: rmb6287@psu.edu
- Course: CMPSC 472-002, Fall 2025

Notes:
- Dwarves “go to work” can be any order
- After poisoning, “come home” can be any order except:
    - Lunch FIFO: dwarves eat in the order they washed
    - “Lets her stay”: Dwarf 1 → Dwarf 2 → Dwarf 3
    - Queen realizes only after all three say “lets her stay”
    - Print is atomic
    - Funeral starts after all dwarves return; all three place casket; last ends program

- BACI string table small, so condensed print text