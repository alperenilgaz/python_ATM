# python_ATM

import time

print("""*********

ILG ATM
-------

İŞLEMLER :

1) Bakiye sorgulama
2) Para çekme
3) Para yatırma
4) havale
***kart iadesi için 'q' basın.***
*********""")
bakiye=1000

while True:
    işlem=input("yapacağınız işlemi seçiniz : ")
    if(işlem=="q"):
        print("kartınızı iade ediliyor...")
        time.sleep(1)
        break

    elif(işlem=="1"):
        print("bakiyeniz hesaplanıyor...")
        time.sleep(1)
        print("mevcut bakiyeniz : {}".format(bakiye))
        break
    elif(işlem=="2"):
        tutar=int(input("çekeceğiniz miktarı giriniz : "))
        if(tutar>bakiye):
            print("yetersiz bakiye lütfen bakiyenizi kontrol edip tekrar deneyiniz. Bakiye : {}".format(bakiye))
        else:
            print("Çektiğiniz tutar hazırlanıyor...")
            time.sleep(1)
            bakiye = bakiye - tutar
            print("kalan bakiyeniz : {}".format(bakiye))
            print("paranızı  ve kartınızı lütfen bölmeden almayı unutmayın. İyi günler")
            break

    elif(işlem=="3"):
        tutar=int(input("lütfen yatıracağınız miktarı giriniz : "))
        bakiye+=tutar
        print("Para başarıyla hesabınıza aktarıldı . Mevcut bakiyeniz : {}".format(bakiye))

    elif(işlem=="4"):
        isim=input("hesabına para gönderceğiniz kişinin ismini soyismini girin : ")
        tutar=int(input("hesaba göndereceğiniz tutarı giriniz :"))
        if(tutar>bakiye):
            print("yetersiz bakiye Ana menüye gönderiliyorsunuz...")
            time.sleep(1)
        else:
            bakiye-=tutar
            print("{} adlı kişini hesabına {}TL başarıyla gönderildi.".format(isim,tutar))
            print("kalan bakiyeniz : {}".format(bakiye))
            break
    else:
        print("Seçtiğiniz işlem mevcut değil daha sonra tekrar deneyiniz")





