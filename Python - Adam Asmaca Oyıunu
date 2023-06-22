

-----------------------------------------------------------------------------------------

import random

kelimeler = ["egea",
             "punto",
             "tofaş",
             "ferrari",
             "ford",
             "dacia",
             "mustang",
             "dooker"] #adam asmaca oyunu içinde kullanılacak kelimeler listesi

adamresim = ["""
   +---+
   |   |
       |
       |
       |
       |
--------""","""
   +---+
   |   |
   O   |
       |
       |
       |
--------""",
            """
   +---+
   |   |
   O   |
   |   |
       |
       |
--------""", """
   +---+
   |   |
   O   |
  /|   |
       |
       |
--------""", """
   +---+
   |   |
   O   |
  /|\  |
       |
       |
--------""", """
   +---+
   |   |
   O   |
  /|\  |
  /    |
       |
--------""","""
   +---+
   |   |
   O   |
  /|\  |
  / \  |
       |
--------"""] #oyun için kullanılacak çizim

uretilensayi = random.randint(0,len(kelimeler)-1)
# print(uretilensayi) # listeye göre rastgele sayı üretme

secilenkelime = kelimeler[uretilensayi]
# print(secilenkelime) # listeye göre uretilen sayının karşılığı olan kelime
# python ile temel ve basit seviyede türkçe Kelime Tahmin Oyunu kodları
print("Adam Asmaca Oyunu - Python\n\n\n") #başlık

print("TÜRETİLEN KELİME : " , uretilensayi , secilenkelime) #türetilen kelimeyi ekrana yazdırma
# gizlisecilenkelime : "_" uzunluğunu belirler. (secilen kelime uzunluğu kadar verir.)
gizlisecilenkelime = "_,"*len(secilenkelime) #len komutu herhangi bir verinin uzunluğunu ölçer.
# oyun içinde kullanılacak kelime için kelime boyutu kadar '_' kullanmak.
gizlisecilenkelime = gizlisecilenkelime.split(",") # split komutu ile seçilen kelimedeki "," kaldırır.
gizlisecilenkelime.pop()
# print(gizlisecilenkelime)

karaktercan = 0 # adam asmacadaki oyuncunun hakkının başlangıç sayısı
# 0 dan başlar 5 e kadar gider toplam 5 hak olduğunu temsil eder.
program = True # programın çalışmasını temsil eder.Program devam eder.
win = False # kazanma fonksiyonu bu aşamada iptal edilir.
buldugumkelimeler = [] # oyun esnasında kullanıcı tarafından girilen kelimeler
yazigosterimi = True

while program and karaktercan != 6: # program ve karaktercan sayısı 6'ya eşit olamaz.
                                    # çünkü kullanıcının toplam 5 hakkı var. 6 yaparsa kaybeder.
    if yazigosterimi:
        print("\n\n\n")
        print(adamresim[karaktercan]) # adam asmaca oyununun çizimini , oyun hakkına göre ekrana ver.
        print(''.join(gizlisecilenkelime)) # oyunda kullanılacak olan kelimeyi verir.
    else:
        yazigosterimi = True
    tahmin = input("Kelime Veya Harf Giriniz : ")
    # tahmin : oyun içinde yazılacak harf veya kelime
    if len(tahmin) > 1: # Kelime için
        if secilenkelime == tahmin: # secilen kelime ve tahmin birbirine eşit ise eğer ,
            gizlisecilenkelime[0:] = secilenkelime # oyunda kullanılacak olan kelimeyi 0'dan sona
                                                   # kadar tamamlarsan secilen kelimeyi bulmuş olursun.
            win = True # yukarıdaki şart'ı sağlarsan oyunu kazanmış oluyorsun yani win : true olmakta.
            program = False # win true olduğu için programın tekrar etmesini engellemek için , false olur.
    else: # eğer 2. koşul için ;
        if tahmin in buldugumkelimeler: # oyun sırasında ekrana yazdığım harfler veya kelimeler tahmin ile ,
                                            # uyuşuyor ise "=" eğer ,
            print(f"\n'{tahmin}' Sen bu harfi daha önce buldun ... \n Lütfen Tekrar Deneyin \n")
            # ekrana tahmin yani ekrana girilen kelime/harf girilir . Yukarıdaki ifade gelir. Koşul sağlanıyorsa.
            yazigosterimi = False
            continue # program devam eder.
        if  secilenkelime.find(tahmin) == -1: #secilen kelime içinde tahmin harf'i yok ise ,
            karaktercan += 1 # karaktercan ' ı + 1 eklenir. Yani hakkın 5 ken 4 olur.
        else: # yukarıdaki koşul olmazsa eğer ,
            if tahmin not in buldugumkelimeler: # tahmin, bulduğum kelimeler & harfler'in içinde değilse ,
                buldugumkelimeler.append(tahmin) # bulduğumkelimeler içine tahmin'i ekle.
            for i in range(0 , len(secilenkelime)): # i : index . i , seçilen kelime değişkeninin her karakterine ,
                if tahmin == secilenkelime[i]:  # işlem yapar . tahmin == ise secilenkelimenin index'ine .
                    gizlisecilenkelime[i] = tahmin # yukarıdaki koşul sağlanıyorsa aşağıdaki koşul uygulanır.
            # 146 - 148 : Bu kodun amacı, kullanıcının girdiği tahmin karakterini secilenkelime dizesindeki
            # her bir karakterle karşılaştırarak doğru tahminleri gizlisecilenkelime dizisindeki
            # uygun karakterlere atamaktır.
        if secilenkelime == ''.join(gizlisecilenkelime): # başta programın seçtiği kelime eşit ise
            win = True  # oyun kazanılır.                                 # gizlisecilenkelime eklenir.
            program = False #oyun kazanıldıysa program döngüsü durdurulur.

    if win:       # eğer kazandıysa :
        print(adamresim[karaktercan])
        # karaktercan adlı bir değişken, doğru tahmin edilmiş toplam karakter
        # sayısını temsil eder ve bu sayı, adamresim listesindeki resimlerin indeksini belirler.
        print(''.join(gizlisecilenkelime))
        # gizlisecilenkelime adlı dize, doğru tahmin edilmiş tüm karakterleri içeren bir dizeye dönüştürülür
        # ve bu dize ekrana yazdırılır. "join()" metodu, dize öğelerini birleştirerek yeni bir dize oluşturur.
        print(f"Tebrikler {secilenkelime} kelimesini buldunuz ! ") #oyunda seçilen kelime string ifade içine ekle.
        # Son olarak, oyuncuya "TEBRİKLER" mesajı verilerek, doğru tahmin ettiği kelimeyi gösterir.

    if karaktercan == len(adamresim) -1 :
        print(adamresim[karaktercan])
        print(f"Oyunu Kaybettiniz , Kelime : {secilenkelime}")
