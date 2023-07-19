# OAC

#Loop <br/>

>>> c <<< <br/>

while(save[i] == k) <br/>
  i++ <br/>

>>> MIPS <<< <br/>

registradores -> save = $s6 = 4; i = $s3 = 0; k = $s5 = 10 <br/>

multiplicar por 4 é o mesmo de deslocar duas casas à esquerda (em binário) <br/>
>>funcional somente para potênica de 2 <br/>
<br/>
sll $s3, $s3, 2 //"$s3 * 4" <br/>
add $t1, $s6, $s3 //save [i] === $s6 + $s3 * 4 //armazena o valor em $t1  <br/>
 <br/>
Loop:  <br/>
  beq $t1, $s5, Incr <br/>
  j Fim <br/>
 <br/>
Incr: <br/>
  addi $s3, $s3, 1  <br/>
  j Loop <br/>
 <br/>
Fim:


-> LOOP infinito

ADDIU $t0, $t0, 0
ADDIU $t0, $t0, 10

SW $t0, 0($s6)
SW $t0, 4($s6)
SW $t0, 8($s6)
SW $t0, 12($s6)

ANDI $t0, $t0, 0
ADDIU $t0, $t0, 1

SW $t0, 16($s6)

inicio:
 SLL $s3, $s3, 2
 ADDU $t1, $s6, $s3
 LW $t0, 0($t1)
    
loop:
 BEQ $t1, $s5, inc
 J fim

inc:
 ADDIU $s3, $s3, 1
 J loop

fim:
