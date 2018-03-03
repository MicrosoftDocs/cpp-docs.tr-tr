---
title: "Veri türü aralıkları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- float keyword [C++]
- char keyword [C++]
- unsigned long
- __wchar_t keyword [C++]
- unsigned short int [C++]
- enum keyword [C++]
- unsigned char keyword [C++]
- integer data type [C++], data type ranges
- int data type
- data types [C++], ranges
- unsigned int [C++]
- short data type
- short int data
- signed types [C++], data type ranges
- long long keyword [C++]
- long double keyword [C++]
- double data type [C++], data type ranges
- signed short int [C++]
- unsigned short
- sized integer types
- signed int [C++]
- signed long int [C++]
- signed char keyword [C++]
- wchar_t keyword [C++]
- long keyword [C++]
- ranges [C++]
- unsigned types [C++], data type ranges
- floating-point numbers [C++]
- data type ranges
- ranges [C++], data types
- long int keyword [C++]
- unsigned long int [C++]
ms.assetid: 3691ceca-05fb-4b82-b1ae-5c4618cda91a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af0601299046276c135571be2bac615df1571140
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="data-type-ranges"></a>Veri Türü Aralıkları
Visual C++ 32 bit ve 64-bit derleyicileri bu makalenin sonraki bölümlerinde tablosunda türlerini kabul eder.  
  
-   `int` (`unsigned int`)  
  
-   `__int8` (`unsigned __int8`)  
  
-   `__int16` (`unsigned __int16`)  
  
-   `__int32` (`unsigned __int32`)  
  
-   `__int64` (`unsigned __int64`)  
  
-   `short` (`unsigned short`)  
  
-   `long` (`unsigned long`)  
  
-   `long` `long` (`unsigned long long`)  
  
 Adını iki alt çizgi ile başlıyorsa (`__`), standart olmayan veri türüdür.  
  
 Aşağıdaki tabloda belirtilen aralıkları kapsayıcı-kapsayıcı.  
  
|Tür adı|Bayt|Diğer adlar|Aralık, değerleri|  
|---------------|-----------|-----------------|---------------------|  
|int|4|imzalı|-2,147,483,648 için 2.147.483.647|  
|unsigned int|4|imzalanmamış|0 için 4.294.967.295|  
|__int8|1.|char|-128 ile 127|  
|İmzasız __int8|1.|unsigned char|0-255|  
|__int16|2|kısa, short int, imzalı short int|-32.768 için 32.767|  
|İmzasız __int16|2|İmzasız short, imzasız short int|0 ile 65.535 arasındaki|  
|__int32|4|İmzalı, imzalı int, int|-2,147,483,648 için 2.147.483.647|  
|İmzasız __int32|4|İmzasız, imzalanmamış int|0 için 4.294.967.295|  
|__int64|8|uzun uzun, uzun uzun imzalı|-9,223,372,036,854,775,808 için 9,223,372,036,854,775,807|  
|İmzasız __int64|8|İmzasız long long|0 için 18,446,744,073,709,551,615|  
|bool|1.|yok|doğru veya yanlış|  
|char|1.|yok|-Varsayılan olarak 128 ile 127<br /><br /> 0 ile kullanarak derlendiğinde 255 [/J](../build/reference/j-default-char-type-is-unsigned.md)|  
|İmzalı char|1.|yok|-128 ile 127|  
|unsigned char|1.|yok|0-255|  
|short|2|short int, imzalı short int|-32.768 için 32.767|  
|imzasız short|2|imzasız short int|0 ile 65.535 arasındaki|  
|long|4|uzun tamsayı, imzalı uzun tamsayı|-2,147,483,648 için 2.147.483.647|  
|imzasız long|4|imzasız long int|0 için 4.294.967.295|  
|long long|8|yok (ancak eşdeğer __int64)|-9,223,372,036,854,775,808 için 9,223,372,036,854,775,807|  
|İmzasız long long|8|yok (ancak eşdeğer imzasız __int64)|0 için 18,446,744,073,709,551,615|  
|enum|Değişir|yok| |  
|float|4|yok|3.4e +/-38 (7 basamak)|  
|çift|8|yok|1.7E +/-308 (15 basamak)|  
|uzun çift|Double ile aynı|yok|Double ile aynı|  
|wchar_t|2|__wchar_t|0 ile 65.535 arasındaki|  
  
 Nasıl kullanıldığı hakkında bağlı olarak, bir değişken `__wchar_t` bir joker karakter türü veya çok baytlı karakter türü belirler. Kullanım `L` önek önce bir karakter veya dize geniş karakter türü sabiti atamak sabiti.  
  
 `signed`ve `unsigned` dışında herhangi bir tam sayı türü ile birlikte kullanabileceğiniz değiştiricileri olan `bool`. Unutmayın `char`, `signed char`, ve `unsigned char` mekanizmaları aşırı yüklemesi ve şablonlar gibi amaçlarını birbirinden farklı üç içindir.  
  
 `int` Ve `unsigned int` türleri dört bayt boyutuna sahip. Ancak, taşınabilir kod boyutuna bağlı olmaması gerekir `int` çünkü standart dil bu uygulamaya özel olarak izin verir.  
  
 C/C++ Visual Studio'da boyutlu tamsayı türleri de destekler. Daha fazla bilgi için bkz: [__int8, \__int16, \__int32, \__int64](../cpp/int8-int16-int32-int64.md) ve [tamsayı sınırları](../cpp/integer-limits.md).  
  
 Her tür boyutlarının kısıtlamaları hakkında daha fazla bilgi için bkz: [temel türleri](../cpp/fundamental-types-cpp.md).  
  
 Numaralandırılmış türler aralığını dil bağlamı bağlı olarak değişir ve derleyici bayrakları belirtilmiş. Daha fazla bilgi için bkz: [C numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md) ve [numaralandırmalar](../cpp/enumerations-cpp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Temel türler](../cpp/fundamental-types-cpp.md)