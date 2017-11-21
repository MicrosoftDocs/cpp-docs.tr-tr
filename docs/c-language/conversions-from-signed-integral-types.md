---
title: "İmzalı tam sayı türlerinden dönüştürmeler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- integral conversions, from signed
- integers, converting
- conversions [C++], integral
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
ms.assetid: 5eea32f8-8b14-413d-acac-c063b3d118d7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ccda8d6fa2573245f34a38f327395955bf92fdc2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="conversions-from-signed-integral-types"></a>İmzalı Tam Sayı Türlerinden Dönüştürmeler
İmzalı bir tamsayı işaretsiz tamsayıya eşit veya daha büyük boyutta dönüştürülür ve imzalı tamsayı değeri negatif olmadığında değiştirilmemiş bir değerdir. Dönüştürme oturum imzalı tamsayı genişletme tarafından yapılır. İmzalı bir tamsayı, yüksek sıralı BITS kesilip daha kısa bir imzalı tamsayıya dönüştürülür. Bu örnekte gösterildiği gibi sonucu imzasız bir değer olarak yorumlanır.  
  
```  
int i = -3;  
unsigned short u;  
  
u = i;   
printf_s( "%hu\n", u );  // Prints 65533  
  
```  
  
 İmzalı bir tamsayı, kayan bir değere dönüştürüldüğünde bazı duyarlık ne zaman kaybolabilir dışında hiçbir bilgi kaybolur bir **uzun tamsayı** veya **imzasız long int** değeri için dönüştürülür bir **float** değeri.  
  
 İmzalı tam sayı türlerinden dönüştürmeler aşağıdaki tabloda özetlenmiştir. Bu tablo varsayar **char** türü varsayılan olarak işaretli. İçin varsayılan değeri değiştirmek için bir derleme zamanı seçeneği kullanıyorsanız **char** tür imzasız için verilen dönüştürmeleri [imzasız tam sayı türlerinden dönüştürmeler](../c-language/conversions-from-unsigned-integral-types.md) tablosu **imzasız char**  türü geçerli aşağıdaki tabloda, imzalı tam sayı türlerinden dönüştürmeler Dönüşümlerde yerine.  
  
### <a name="conversions-from-signed-integral-types"></a>İmzalı Tam Sayı Türlerinden Dönüştürmeler  
  
|Başlangıç|Bitiş|Yöntem|  
|----------|--------|------------|  
|**char**1|**kısa**|Oturum genişletme|  
|**char**|**uzun**|Oturum genişletme|  
|**char**|**İmzasız char**|Desen korumak; yüksek sıralı bit işlevi oturum bit kaybeder.|  
|**char**|**İmzasız short**|Oturum-genişletmek için **kısa**; Dönüştür **kısa** için **kısa imzalanmamış**|  
|**char**|**İmzasız long**|Oturum-genişletmek için **uzun**; Dönüştür **uzun** için **uzun imzalanmamış**|  
|**char**|**kayan nokta**|Oturum-genişletmek için **uzun**; Dönüştür **uzun** için **float**|  
|**char**|**çift**|Oturum-genişletmek için **uzun**; Dönüştür **uzun** için **çift**|  
|**char**|**uzun çift**|Oturum-genişletmek için **uzun**; Dönüştür **uzun** için **çift**|  
|**kısa**|**char**|Düşük düzey baytı korur|  
|**kısa**|**uzun**|Oturum genişletme|  
|**kısa**|**İmzasız char**|Düşük düzey baytı korur|  
|**kısa**|**İmzasız short**|Bit desenini korumak; yüksek sıralı bit işlevi oturum bit kaybeder.|  
|**kısa**|**İmzasız long**|Oturum-genişletmek için **uzun**; Dönüştür **uzun** için **uzun imzalanmamış**|  
|**kısa**|**kayan nokta**|Oturum-genişletmek için **uzun**; Dönüştür **uzun** için **float**|  
|**kısa**|**çift**|Oturum-genişletmek için **uzun**; Dönüştür **uzun** için **çift**|  
|**kısa**|**uzun çift**|Oturum-genişletmek için **uzun**; Dönüştür **uzun** için **çift**|  
|**uzun**|**char**|Düşük düzey baytı korur|  
|**uzun**|**kısa**|Düşük düzey word koru|  
|**uzun**|**İmzasız char**|Düşük düzey baytı korur|  
|**uzun**|**İmzasız short**|Düşük düzey word koru|  
|**uzun**|**İmzasız long**|Bit desenini korumak; yüksek sıralı bit işlevi oturum bit kaybeder.|  
|**uzun**|**kayan nokta**|Olarak temsil eden **float**. Varsa **uzun** olamaz tam olarak ifade edilen, bazı duyarlık kaybolur.|  
|**uzun**|**çift**|Olarak temsil eden **çift**. Varsa **uzun** tam olarak temsil edilemez bir **çift**, bazı duyarlık kaybolur.|  
|**uzun**|**uzun çift**|Olarak temsil eden **çift**. Varsa **uzun** tam olarak temsil edilemez bir **çift**, bazı duyarlık kaybolur.|  
  
 1. Tüm **char** girişleri varsayın **char** türü varsayılan olarak işaretli.  
  
 **Microsoft özel**  
  
 Microsoft 32-bit C derleyici için tamsayı eşdeğer olan bir **uzun**. Dönüştürme bir **int** değeri aynı geçer bir **uzun**.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama dönüşümleri](../c-language/assignment-conversions.md)