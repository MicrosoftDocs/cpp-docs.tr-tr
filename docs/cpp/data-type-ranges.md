---
title: Veri türü aralıkları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d55a2102299957a40cd9f742f91868ee2b5b849b
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407682"
---
# <a name="data-type-ranges"></a>Veri Türü Aralıkları
Visual C++ 32 bit ve 64-bit derleyiciler bu makalenin devamındaki tablosunda türlerini tanır.  
  
-   `int` (`unsigned int`)  
  
-   `__int8` (`unsigned __int8`)  
  
-   `__int16` (`unsigned __int16`)  
  
-   `__int32` (`unsigned __int32`)  
  
-   `__int64` (`unsigned __int64`)  
  
-   `short` (`unsigned short`)  
  
-   `long` (`unsigned long`)  
  
-   `long` `long` (`unsigned long long`)  
  
 Adı iki alt çizgi ile başlıyorsa (`__`), bir veri türü standart değildir.  
  
 Aşağıdaki tabloda belirtilen aralıklarını baştaki.  
  
|Tür adı|Bayt|Diğer adları|Değer aralıkları|  
|---------------|-----------|-----------------|---------------------|  
|**int**|4|**İmzalı**|-2.147.483.648 için 2.147.483.647|  
|**işaretsiz int**|4|**İşaretsiz**|0 için 4.294.967.295'e|  
|**__int8**|1.|**char**|-128 ila 127 arasında|  
|**İmzasız __int8**|1.|**İmzasız char**|0 ile 255 arasında|  
|**__int16**|2|**kısa**, **kısa tamsayı**, **imzalı short int**|-32.768 için 32.767|  
|**İmzasız __int16**|2|**işaretsiz**, **imzasız short int**|0 ile 65.535 arasındaki|  
|**__int32 türünün int**|4|**İmzalı**, **signed int**, **int**|-2.147.483.648 için 2.147.483.647|  
|**İmzasız __int32 türünün int**|4|**İmzasız**, **işaretsiz int**|0 için 4.294.967.295'e|  
|**__int64**|8|**uzun uzun**, **imzalanmış long long**|-9,223,372,036,854,775,808 için 9.223.372.036.854.775.807|  
|**imzalanmamış __int64**|8|**İmzasız uzun uzun**|0 için 18,446,744,073,709,551,615|  
|**bool**|1.|yok|**false** veya **true**|  
|**char**|1.|yok|-Varsayılan olarak 128 ile 127<br /><br /> 0 ila kullanılarak derlendiğinde 255 [/J](../build/reference/j-default-char-type-is-unsigned.md)|  
|**İmzalı char**|1.|yok|-128 ila 127 arasında|  
|**İmzasız char**|1.|yok|0 ile 255 arasında|  
|**short**|2|**kısa tamsayı**, **imzalı short int**|-32.768 için 32.767|  
|**İmzasız short**|2|**İmzasız short int**|0 ile 65.535 arasındaki|  
|**long**|4|**Long int**, **imzalı long int**|-2.147.483.648 için 2.147.483.647|  
|**İmzasız long**|4|**İmzasız long int**|0 için 4.294.967.295'e|  
|**Long long**|8|Hiçbiri (ancak **__int64**)|-9,223,372,036,854,775,808 için 9.223.372.036.854.775.807|  
|**İmzasız uzun uzun**|8|Hiçbiri (ancak **unsigned __int64**)|0 için 18,446,744,073,709,551,615|  
|**enum**|Değişir|yok| |  
|**float**|4|yok|3.4e +/-38 (7 basamak)|  
|**double**|8|yok|1.7E +/-308 (15 basamak)|  
|**uzun çift**|aynı **çift**|yok|Aynı **çift**|  
|**wchar_t**|2|**__wchar_t**|0 ile 65.535 arasındaki|  
  
 Nasıl kullanıldığına bağlı olarak, bir değişken **__wchar_t** geniş karakter türü veya çok baytlı karakter türünü belirtir. Kullanım `L` önek önce bir karakter veya dize sabiti geniş karakter türü sabiti belirtmek için.  
  
 **İmzalı** ve **işaretsiz** dışında herhangi bir tamsayı türü ile kullanabileceğiniz değiştiricilerdir **bool**. Unutmayın **char**, **signed char**, ve **imzasız char** aşırı yükleme ve şablonlar gibi mekanizmaların amaçlarına yönelik üç farklı türü şunlardır.  
  
 **İnt** ve **işaretsiz int** türleri dört baytlık boyuta sahiptir. Ancak, taşınabilir kod boyutuna bağlı olmamalıdır **int** dil standardı uygulamaya özgü olmasını sağladığından.  
  
 Visual Studio'da C/C++, ayrıca ölçekli tamsayı türlerini destekler. Daha fazla bilgi için [__int8, \__int16, \__int32, \__int64](../cpp/int8-int16-int32-int64.md) ve [tamsayı sınırları](../cpp/integer-limits.md).  
  
 Her türün boyut sınırlamaları hakkında daha fazla bilgi için bkz. [temel türler](../cpp/fundamental-types-cpp.md).  
  
 Numaralanmış türlerin aralığı dil bağlamına bağlı olarak değişir ve belirtilen derleyici bayraklarına. Daha fazla bilgi için [C numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md) ve [numaralandırmalar](../cpp/enumerations-cpp.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Temel Türler](../cpp/fundamental-types-cpp.md)