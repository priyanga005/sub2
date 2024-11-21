    MOV     R0, #BUFFER_1      ; Load base address of BUFFER_1
    MOV     R1, #BUFFER_2      ; Load base address of BUFFER_2
    MOV     R2, #BUFFER_3      ; Load base address of BUFFER_3
    MOV     R3, #0             ; Initialize index

LOOP:
    LDR     R4, [R0, R3]       ; Load value from BUFFER_1 at index R3
    LDR     R5, [R1, R3]       ; Load value from BUFFER_2 at index R3
    ADD     R6, R4, R5         ; Add values and store result in R6
    STR     R6, [R2, R3]       ; Store result in BUFFER_3

    ADD     R3, R3, #1         ; Increment index
    CMP     R3, #100           ; Check if all elements processed
    BLT     LOOP               ; If not, continue the loop
