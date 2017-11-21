---
title: "Dönüş türü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- function return types
- return values [C++], function procedures
- function return types, syntax
- return values [C++]
- data types [C++], function return types
- return keyword [C++], function return types
- functions [C++], return types
ms.assetid: 3e5b8a97-b341-48c5-8be8-8986980ef586
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4faa6143342d8765fce460a653090152c0b10417
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="return-type"></a>Dönüş Türü
Bir işlevin dönüş türü işlev tarafından döndürülen değerin türü ve boyutunu belirler ve aşağıdaki sözdiziminde tür belirteci karşılık gelir:  
  
## <a name="syntax"></a>Sözdizimi  
 *işlev tanımı*:  
 *bildirim tanımlayıcıları* kabul*özniteliği seq* kabul*bildirimcisi bildirimi listesi* kabul*bileşik deyim*  
  
 /\**özniteliği seq* Microsoft Specific * /  
  
 *bildirim tanımlayıcıları*:  
 *depolama sınıfı tanımlayıcısı bildirim tanımlayıcıları* iptal et  
  
 *tür belirteci bildirim tanımlayıcıları* iptal et  
  
 *tür niteleyicisi bildirim tanımlayıcıları* iptal et  
  
 *tür belirteci*:  
 **void**  
  
 **char**  
  
 **kısa**  
  
 **int**  
  
 **uzun**  
  
 **kayan nokta**  
  
 **çift**  
  
 **İmzalı**  
  
 **İmzasız**  
  
 *yapı veya birleşim belirticisi*  
  
 *Liste belirticisi*  
  
 *TypeDef adı*  
  
 *Tür belirteci* herhangi temel belirtebilirsiniz yapısı veya birleşim türü. Dahil etmezseniz *tür belirteci*, dönüş türü `int` varsayılır.  
  
 İşlev tanımında belirtilen dönüş türü bildirimlerden programı başka bir yerinde işlevinin dönüş türü eşleşmesi gerekir. Bir işlev bir değer döndürür olduğunda bir `return` bir ifade içeren deyimi gerçekleştirilir. Gerekli ve işlev çağrıldı noktasına döndürülen dönüş değeri türe dönüştürülüp ifade değerlendirilir. Bir işlevin dönüş türüyle bildirilirse `void`, bir ifade içeren bir dönüş ifadesi bir uyarı oluşturur ve ifade değerlendirilmez.  
  
 Aşağıdaki örnekler işlevi dönüş değerleri gösterir.  
  
```  
typedef struct    
{  
    char name[20];  
    int id;  
    long class;  
} STUDENT;  
  
/* Return type is STUDENT: */  
  
STUDENT sortstu( STUDENT a, STUDENT b )  
{  
    return ( (a.id < b.id) ? a : b );  
}  
```  
  
 Bu örnek tanımlar `STUDENT` ile yazın bir `typedef` bildirimi ve işlevi tanımlayan `sortstu` olmasını `STUDENT` dönüş türü. İşlev seçer ve iki yapısı değişkenlerinin birini döndürür. Sonraki çağrılarında işlevi derleyici denetler bağımsız değişken türleri olduğundan emin olmak için `STUDENT`.  
  
> [!NOTE]
>  Tüm yapısı yerine yapısı işaretçileri geçirerek verimliliği artırılmış.  
  
```  
char *smallstr( char s1[], char s2[] )  
{  
    int i;  
  
    i = 0;  
    while ( s1[i] != '\0' && s2[i] != '\0' )  
        i++;  
    if ( s1[i] == '\0' )  
        return ( s1 );  
    else  
        return ( s2 );  
}  
```  
  
 Bu örnek, bir karakter dizisi için bir işaretçi döndüren bir işlev tanımlar. İşlev iki karakter dizileri (dize) bağımsız değişkenleri olarak alır ve bir işaretçi Kısa döndürür iki dizeleri. Bir dizi için bir işaretçi işaret ilk dizi öğeleri ve türünü; Bu nedenle, işlevin dönüş türünü yazmak için bir işaretçidir `char`.  
  
 İşlevleri bildirmelisiniz olmayan `int` dönüş türü, çağırmadan önce doğru türü bağımsız değişkenleri ve dönüş değerleri denetleniyor etkin böylece prototipleri önerilir ancak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C işlev tanımları](../c-language/c-function-definitions.md)