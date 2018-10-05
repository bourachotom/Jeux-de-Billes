# Jeux-de-Billes
from random import randint

def computer():
    print("")
    print("Je prends",s,"bille(s)")

def FNB():
    n=int(input("Choisissez un nombre entre 1 et 3_"))
    while n>3 or n<1:
        print("Ce nombre n'est pas un nombre compris entre 1 et 3 >:(")
        n=int(input("Choisissez un nombre entre 1 et 3 "))
    return n
    
        
p=0
z=1
while z==1:
    print("Bonjour! Choisissez la difficulté : 1 pour mode facile, 2 pour mode expert.")
    m=int(input())
    if m==2:
        b=int(input("Choisissez le nombre de billes dans le sac:"))
        while b>0:
            n=FNB()
            b=b-n
            print("Billes restantes =", b)
            if b<=0:
                print("Vous perdez :-(")
            elif b>0:
                s=(b%4)
                if s==0:
                    b=b-3
                    print("je prends 3 billes.")
                elif s==1:
                  a=randint(1,3)
                  print("Je prends",a,"bille(s)")
                  b=b-a
                elif s>0:
                  b=b-s+1
                  print("je prends",s-1,"billes.")
                  
                
            print("")
            print("Billes restantes=", b)
        if b<=0:
            print("Vous gagnez :-)")
            p=p+1
    elif m==1:
        b=int(input("Choisissez le nombre de billes dans le sac:"))
        while b>0:
            print("Choisissez un nombre entre 1 et 3_",end="")
            n=int(input())
            b=b-n
            print("Billes restantes=",b)
            if b<=0:
                print("Vous perdez :-(")
            elif b>0:
                a=randint(1,3)
                print("")
                print("Je prends",a,"bille(s)")
                b=b-a
                print("Billes restantes=",b)
            if b<=0:
                print("Vous gagnez :-)")
                p=p+1
    print("")
    print("parties gagnée(s)=",p)
    print("Voulez-vous rejouer? Tapez 'oui' ou 'non':")
    y=str(input())
    if y=="oui":
        z=1
    elif y=="non":
        print("Aurevoir")
        z=0
