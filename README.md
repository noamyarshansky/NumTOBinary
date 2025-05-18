def decimal_to_twos_complement(number, bits):
    min_val = -2**(bits - 1)
    max_val = 2**(bits - 1) - 1
    if number < min_val or number > max_val:
        return f"שגיאה: המספר {number} חורג מהטווח האפשרי ל-{bits} סיביות: ({min_val} עד {max_val})"
    
    if number >= 0:
        binary = bin(number)[2:].zfill(bits)
    else:
        binary = bin((1 << bits) + number)[2:]
    
    return binary

print (decimal_to_twos_complement(-201,16))