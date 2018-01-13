---
title: "IEEE kayan Noktası temsili | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- float keyword
- real*8 value
- floating-point numbers, IEEE representation
- double data type, floating-point representation
- IEEE floating point representation
- real*10 value
- long double
- real*4 value
ms.assetid: 537833e8-fe05-49fc-8169-55fd0314b195
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17fae0cbb16208d5c7e7346f354f3501e4803d96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ieee-floating-point-representation"></a>IEEE Kayan Noktası Temsili
Microsoft Visual C++ IEEE sayısal standartları ile uyumludur. Gerçek sayılar üç iç çeşitleri vardır. Gerçek\*4 ve gerçek\*8'de Visual C++ kullanılır. Gerçek\*4 word kullanılarak bildirilen **float**. Gerçek\*8 word kullanılarak bildirilen **çift**. Windows 32-bit programlama içinde `long double` veri türü eşlemeleri için **çift**. Yoktur, ancak gerçek kullanarak hesaplamalar için derleme dili desteği * 10 veri türü.  
  
 Değerler şu şekilde depolanır:  
  
|Değer|Olarak depolanması|  
|-----------|---------------|  
|Gerçek * 4|oturum bit, 8 bit üs, 23 bit Mantis|  
|Gerçek * 8|oturum bit, 11 bit üs, 52 bit Mantis|  
|Gerçek * 10|oturum bit, 15 bit üs, 64-bit Mantis|  
  
 Gerçek * 4 ve gerçek\*8 biçimleri, yalnızca 23 veya 52 BITS depolanan olsa da gerçekte 24 veya 53 BITS, mantisler; bu nedenle, bellekte depolanmaz Mantis kabul başında 1 yoktur. Gerçek\*10 biçimi aslında bu bit depolar.  
  
 Üs yarısı olası değerlerine göre eğilimi nedeniyle. Bu, bu sapması gerçek üs almak için saklı üs gelen çıkarma anlamına gelir. Saklı üs sapması'dan küçük, Negatif üs gerçekte olur.  
  
 Üsler gibi ağırlıklı:  
  
|Üs|Tarafından ağırlıklı|  
|--------------|---------------|  
|8 bit (gerçek * 4)|127|  
|11-bit (gerçek * 8)|1023|  
|15-bit (gerçek * 10)|16383|  
  
 Bu üs katları değildir; iki tabanların oldukları. Diğer bir deyişle, 8 bit saklı üs en çok 127 olabilir. Değerin 2 ** 127 10 kabaca eşdeğerdir\*\*gerçek gerçek sınırı 38\*4.  
  
 Mantis formun ikili kesir olarak depolanan... 1.XXX. Bu kesir 1 ve 2'den eşit veya daha büyük bir değere sahip. Gerçek sayılar normalleştirilmiş formunda her zaman depolandığını unutmayın; diğer bir deyişle, Mantis sol-Mantis yüksek sıra biti her zaman 1 olacak şekilde, kaydırılacağı uzaklık. Bu bit her zaman 1 olduğundan, (depolanmayan) varsayılır gerçek * 4 ve gerçek\*8 biçimleri. İkili (ondalık değil) noktası yalnızca başında 1 sağda olduğu varsayılır.  
  
 Biçim daha sonra çeşitli boyutları şu şekildedir:  
  
|Biçimi|BYTE 1|BAYT 2|BAYT 3|BAYT 4|...|BAYT n|  
|------------|------------|------------|------------|------------|---------|------------|  
|Gerçek * 4|`SXXX XXXX`|`XMMM MMMM`|`MMMM MMMM`|`MMMM MMMM`|||  
|Gerçek * 8|`SXXX XXXX`|`XXXX MMMM`|`MMMM MMMM`|`MMMM MMMM`|...|`MMMM MMMM`|  
|Gerçek * 10|`SXXX XXXX`|`XXXX XXXX`|`1MMM MMMM`|`MMMM MMMM`|...|`MMMM MMMM`|  
  
 `S`oturum bit temsil eden `X`'s üs bitleri ve `M`'s Mantis bittir. Soldaki bit gerçek varsayılır Not * 4 ve gerçek\*8 biçimleri, ancak "1" mevcut gerçek, bayt 3'te\*10 biçimi.  
  
 İkili noktası doğru kaydırmak için ilk üs unbias ve ardından ikili noktasını sağa taşıyın veya uygun bit sayısı kadar sola.  
  
## <a name="examples"></a>Örnekler  
 Gerçek bazı örnekler verilmiştir * 4 biçimi:  
  
-   Aşağıdaki örnekte, sıfır işaret bitidir ve saklı üs 128 veya 100 0000 0 ile 127 artı 1 ikili. Saklı Mantis (1.). 000 0000 ... Bu nedenle gerçek Mantis biridir 0000 0000, zımni başında 1 ve ikili noktanız, sahip olduğu.  
  
    ```  
                        SXXX XXXX XMMM MMMM ... MMMM MMMM  
    2   =  1  * 2**1  = 0100 0000 0000 0000 ... 0000 0000 = 4000 0000  
    ```  
  
-   Oturum biti ayarlanmış ancak bu + 2 aynıdır. Bu, tüm IEEE kayan nokta sayıları biçimlendirme için geçerlidir.  
  
    ```  
    -2  = -1  * 2**1  = 1100 0000 0000 0000 ... 0000 0000 = C000 0000  
    ```  
  
-   Aynı Mantis üs tek (taraflı 129 ya da 100 0000 1'de ikili değerdir. artırır.  
  
    ```  
    4  =  1  * 2**2  = 0100 0000 1000 0000 ... 0000 0000 = 4080 0000  
    ```  
  
-   Aynı üs Mantis büyükse yarı oranında — buna ait (1.) 100 0000... Bu ikili kesir olduğundan olan, 1 1/2 (kesir basamakları 1/2, 1/4, 1/8 ve benzeri değerleri) 0000 0000.  
  
    ```  
    6  = 1.5 * 2**2  = 0100 0000 1100 0000 ... 0000 0000 = 40C0 0000  
    ```  
  
-   Diğer iki Mantis olarak aynı üs ikiden az 127 ya da ikili 011 1111 1 biridir.  
  
    ```  
    1  = 1   * 2**0  = 0011 1111 1000 0000 ... 0000 0000 = 3F80 0000  
    ```  
  
-   Taraflı üs 126 olduğu 011 1111 0 içinde ikili ve Mantis olduğunu (1.) 100 0000 ... 0000 0000 1 1/2'dir.  
  
    ```  
    .75 = 1.5 * 2**-1 = 0011 1111 0100 0000 ... 0000 0000 = 3F40 0000  
    ```  
  
-   Tam olarak aynı iki dışındaki 1/4 temsil eden bit Mantis ayarlanır.  
  
    ```  
    2.5 = 1.25 * 2**1 = 0100 0000 0010 0000 ... 0000 0000 = 4020 0000  
    ```  
  
-   1/10 ikili olarak yinelenen bir bölümüdür. Mantis 1.6 yalnızca çekingen ve taraflı üs 1.6 16 tarafından bölünür olduğunu söylüyor (Bu 011 1101 1 ondalık 123 olan ikili'dir). Doğru üs 123-127'dir = - çarpılacağı faktörüyle 2 ** -4 = 1/16 anlamına gelir 4. Son bit saklı Mantis yuvarlanan Not — unrepresentable numarası mümkün olduğunca doğru bir şekilde temsil girişimi. (Bunun nedeni, 1/10 ve 1/100 ikili tam olarak gösterilebilir 1/3 ondalık tam olarak gösterilebilir Bunun nedeni benzer.)  
  
    ```  
    0.1 = 1.6 * 2**-4 = 0011 1101 1100 1100 ... 1100 1101 = 3DCC CCCD  
    ```  
  
-   `0  = 1.0 * 2**-128 = all zeros--a special case.`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği](../../build/reference/why-floating-point-numbers-may-lose-precision.md)