# Clump-Finding-Problem
#Given integers L and t, a string Pattern forms an (L, t)-clump inside a (larger) string Genome if there is an interval #of Genome of length L in which Pattern appears at least t times. For example, TGCA forms a (25,3)-clump in the #following Genome: gatcagcataagggtcccTGCAaTGCAtgacaagccTGCAgttgttttac. 
#Clump Finding Problem  Find patterns forming clumps in a string.  
#Given: A string Genome, and integers k, L, and t.  
#Return: All distinct k-mers forming (L, t)-clumps in Genome. 
#Sample Dataset CGGACTCGACAGATGTGAAGAAATGTGAAGACTGAGTGAAGAGAAGAGGAAACACGACACGACATTGCGACATAATGTACGAATGTAATGTGCCTATGGC 5 #75 4  
Sample Output  CGACA GAAGA AATGT


def Clump(RNA,dist,leng,rep):
    salida = {}
    for i in range(len(RNA)-dist):
        segmento = RNA[i:i + dist]
        
        kmeros = {}
        for a in range(len(segmento)-leng):
            kmero= segmento[a: a +leng]
            if kmero not in kmeros:
               kmeros[kmero] = 1
            else:
               kmeros[kmero] = kmeros[kmero] + 1
        for z in kmeros.keys():
            
            if kmeros[z] >= rep:  
                salida[z] = 1
    return salida.keys()
    
print Clump("CGGACTCGACAGATGTGAAGAAATGTGAAGACTGAGTGAAGAGAAGAGGAAACACGACACGACATTGCGACATAATGTACGAATGTAATGTGCCTATGGC",75,5,4)
