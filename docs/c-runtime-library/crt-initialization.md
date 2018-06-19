---
title: CRT başlatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CRT initialization [C++]
ms.assetid: e7979813-1856-4848-9639-f29c86b74ad7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd267ed4c8e21756df653a196ce41b594d41de77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389708"
---
# <a name="crt-initialization"></a>CRT Başlatma
Bu konuda nasıl CRT yerel kodda genel durumlarını başlatır açıklanmaktadır.  
  
 Varsayılan olarak, bağlayıcı, kendi başlatma kodunu sağlar CRT kitaplık içerir. Bu başlangıç kodu CRT kitaplık başlatır, genel başlatıcıları çağırır ve kullanıcı tarafından sağlanan çağıran `main` işlevi konsol uygulamaları için.  
  
## <a name="initializing-a-global-object"></a>Genel nesne başlatılıyor  
 Aşağıdaki kod göz önünde bulundurun:  
  
```  
int func(void)  
{  
    return 3;  
}  
  
int gi = func();  
  
int main()  
{  
    return gi;  
}  
```  
  
 C/C++ Standart göre `func()` önce çağrılmalıdır `main()` yürütülür. Ancak kimin çağırır?  
  
 Tek yönlü bir kesme noktası ayarlamak için bu olduğunu belirlemek için `func()`uygulamada hata ayıklama ve yığın inceleyin. CRT kaynak kodu ile Visual Studio dahil olduğundan, bu mümkündür.  
  
 Yığında işlevleri göz attığınızda, CRT işlev işaretçileri listesini döngü oluşturma ve bunları bulduğu gibi her biri çağrılırken bulabilirsiniz. Bu işlevler olan benzer `func()` veya oluşturucuları sınıf örnekleri için.  
  
 CRT Visual C++ derleyiciden işlev işaretçileri listesini alır. Derleyici global Başlatıcı gördüğünde, dinamik bir başlatıcı oluşturur `.CRT$XCU` bölümüne (burada `CRT` bölüm adı ve `XCU` grup adı). Komutu çalıştırın bu dinamik başlatıcıları listesini elde etmek için **DUMPBIN/all main.obj**ve ardından arama `.CRT$XCU` bölümünde (main.cpp C dosyası değil C++ dosyası olarak derlenmiş olduğunda). Aşağıdakine benzer olacaktır:  
  
```  
SECTION HEADER #6  
.CRT$XCU name  
       0 physical address  
       0 virtual address  
       4 size of raw data  
     1F2 file pointer to raw data (000001F2 to 000001F5)  
     1F6 file pointer to relocation table  
       0 file pointer to line numbers  
       1 number of relocations  
       0 number of line numbers  
40300040 flags  
         Initialized Data  
         4 byte align  
         Read Only  
  
RAW DATA #6  
  00000000: 00 00 00 00                                      ....  
  
RELOCATIONS #6  
                                                Symbol    Symbol  
 Offset    Type              Applied To         Index     Name  
 --------  ----------------  -----------------  --------  ------  
 00000000  DIR32                      00000000         C  ??__Egi@@YAXXZ (void __cdecl `dynamic initializer for 'gi''(void))  
```  
  
 CRT iki işaretçileri tanımlar:  
  
-   `__xc_a` İçinde `.CRT$XCA`  
  
-   `__xc_z` İçinde `.CRT$XCZ`  
  
 Her iki grup dışında tanımlanmış semboller yok `__xc_a` ve `__xc_z`.  
  
 Şimdi, ne zaman bağlayıcı okur çeşitli `.CRT` grupları, bir bölümünde birleştirir ve alfabetik olarak sıralar. Bu, kullanıcı tanımlı genel başlatıcıları anlamına gelir (Visual C++ derleyicisi getirecek `.CRT$XCU`) her zaman sonra gelir `.CRT$XCA` ve önce `.CRT$XCZ`.  
  
 Bölüm şuna benzer:  
  
```  
.CRT$XCA  
            __xc_a  
.CRT$XCU  
            Pointer to Global Initializer 1  
            Pointer to Global Initializer 2  
.CRT$XCZ  
            __xc_z  
```  
  
 Bu nedenle, her ikisi de CRT kitaplık kullanan `__xc_a` ve `__xc_z` başlangıç ve bitiş genel başlatıcıları listesinin, bunlar düzenlenir bellekte görüntü yüklendikten sonra yolu nedeniyle belirlemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)