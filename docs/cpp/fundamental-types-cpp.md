---
title: Temel türleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __int128_cpp
- __wchar_t_cpp
- char_cpp
- double_cpp
- float_cpp
- int_cpp
- long_cpp
- long_double_cpp
- short_cpp
- signed_cpp
- unsigned_cpp
- unsigned_int_cpp
- wchar_t_cpp
dev_langs:
- C++
helpviewer_keywords:
- specifiers [C++], type
- float keyword [C++]
- char keyword [C++]
- __wchar_t keyword [C++]
- signed types [C++], summary of data types
- Integer data type [C++], C++ data types
- arithmetic operations [C++], types
- int data type
- unsigned types [C++], summary of data types
- short data type [C++]
- double data type [C++], summary of types
- long long keyword [C++]
- long double keyword [C++]
- unsigned types [C++]
- signed types [C++]
- void keyword [C++]
- storage [C++], basic type
- integral types, C++
- wchar_t keyword [C++]
- floating-point numbers [C++], C++ data types
- long keyword [C++]
- type specifiers [C++]
- integral types
- long keyword [C++], C++ data types
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c24ee360f1c14aa9b355f45ec1c12877efa306c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417334"
---
# <a name="fundamental-types--c"></a>Temel Türler (C++)
C++'ta temel türleri üç kategoride bölünen: tamsayı, kayan nokta ve void. Tam sayı türleri tam sayılar işleyebilir. Kayan nokta türleri kesirli bölümleri olabilir değerleri belirtme özelliğine sahiptir.  
  
 [Void](../cpp/void-cpp.md) türünü değerler boş kümesini tanımlar. Hiçbir değişken türü `void` belirtilebilir — genel işaretçileri türsüz veya rasgele bildirmek için veri girilen veya öncelikle hiçbir değer döndüren işlevler bildirmek için kullanılır. Herhangi bir ifade bulunabilir açıkça dönüştürülen veya yazmak için cast `void`. Ancak, bu tür ifadeleri aşağıdaki kullandığı sınırlıdır:  
  
-   Bir ifade deyimi. (Bkz [ifadeleri](../cpp/expressions-cpp.md), daha fazla bilgi için.)  
  
-   Virgül işleci sol işleneni. (Bkz [virgül işleci](../cpp/comma-operator.md) daha fazla bilgi için.)  
  
-   Koşullu işleç ikinci ya da üçüncü işleneni (`? :`). (Bkz [koşullu işleç ifadelerle](../cpp/conditional-operator-q.md) daha fazla bilgi için.)  
  
 Aşağıdaki tabloda kısıtlamaları türü boyutlarına açıklanmaktadır. Bu kısıtlamalar Microsoft uyarlamasını bağımsızdır.  
  
### <a name="fundamental-types-of-the-c-language"></a>C++ dili temel tür  
  
|Kategori|Tür|İçindekiler|  
|--------------|----------|--------------|  
|Tam sayıdan kaymaya|`char`|Tür `char` genellikle temel yürütme karakter kümesi üyelerini içeren bir tam sayı türü — varsayılan olarak, Microsoft C++ ASCII budur.<br /><br /> C++ derleyicisi değişkenlerine türü `char`, `signed` `char`, ve `unsigned` `char` farklı türlerine sahip olarak. Türündeki değişkenler `char` için yükseltilen `int` türü varsa gibi `signed` `char` varsayılan olarak, /J derleme seçeneği kullanılmıyorsa. Bu durumda türü olarak davranılır `unsigned` `char` için yükseltilmiş `int` oturum uzantısı olmadan.|  
||`bool`|Tür `bool` iki değerden birini sahip olabilen bir tam sayı türüdür `true` veya `false`. Boyutuna belirtilmedi.|  
||`short`|Tür `short` `int` (ya da yalnızca `short`) türü boyutuna eşit veya bundan büyük bir tam sayı türü `char`, daha kısa veya buna eşit ve yazı tipi boyutu için `int`.<br /><br /> Nesne türü `short` olarak bildirilen `signed` `short` veya `unsigned short`. `Signed short` eşanlamlısı olduğu `short`.|  
||`int`|Tür `int` türü boyutuna eşit veya bundan büyük bir tam sayı türü `short` `int`, daha kısa veya buna eşit ve yazı tipi boyutu için `long`.<br /><br /> Nesne türü `int` olarak bildirilen `signed` `int` veya `unsigned` `int`. `Signed` `int` eşanlamlısı olduğu `int`.|  
||`__int8`, `__int16`, `__int32`, `__int64`|Boyutlu tamsayı `__int n`, burada `n` tamsayı değişken bit cinsinden boyutu. `__int8`, `__int16`, `__int32` ve `__int64` Microsoft'a özgü anahtar sözcükler. Tüm türleri üzerinde tüm mimarileri kullanılabilir. `(__int128` desteklenmiyor.)|  
||`long`|Tür `long` (veya `long` `int`) türü boyutuna eşit veya bundan büyük bir tam sayı türü `int`.<br /><br /> Nesne türü `long` olarak bildirilen `signed` `long` veya `unsigned` `long`. `Signed` `long` eşanlamlısı olduğu `long`.|  
||`long``long`|Büyük imzasız `long`.<br /><br /> Nesne türü `long long` olarak bildirilen `signed` `long long` veya `unsigned` `long long`. `signed` `long long` eşanlamlısı olduğu `long long`.|  
||`wchar_t`, `__wchar_t`|Türünde bir değişken `wchar_t` bir joker karakter veya birden çok baytlı karakter türü belirler. Varsayılan olarak, `wchar_t` yerel türünde, ancak kullanabileceğiniz [/Zc:wchar_t-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) yapmak için `wchar_t` için typedef `unsigned short`. `__wchar_t` Türüdür Microsoft'a özgü eşanlamlısı yerel `wchar_t` türü.<br /><br /> L öneki, joker karakter türü belirlemek için bir karakter ya da dize sabit değeri önce kullanın.|  
|Kayan nokta|`float`|Tür `float` en küçük kayan noktası türü.|  
||`double`|Tür `double` bir kayan büyük nokta türünü veya yazmak için eşittir `float`, ancak daha kısa veya buna eşit yazı tipi boyutu `long` `double`.<br /><br /> Microsoft özel: gösterimini `long double` ve `double` aynıdır. Ancak, `long double` ve `double` ayrı türleridir.|  
||`long double`|Tür `long` `double` bir kayan büyük nokta türünü veya yazmak için eşittir `double`.|  
  
 **Microsoft özel**  
  
 Aşağıdaki tabloda Microsoft c++ temel türleri için gerekli depolama miktarını listeler.  
  
### <a name="sizes-of-fundamental-types"></a>Temel türler boyutları  
  
|Tür|Boyut|  
|----------|----------|  
|`bool`, `char`, `unsigned char`, `signed char`, `__int8`|1 bayt|  
|`__int16`, `short`, `unsigned short`, `wchar_t`, `__wchar_t`|2 bayt|  
|`float`, `__int32`, `int`, `unsigned int`, `long`, `unsigned long`|4 bayt|  
|`double`, `__int64`, `long double`, `long long`|8 bayt|  
  
 **SON Microsoft özel**  
  
 Bkz: [veri türü aralıkları](../cpp/data-type-ranges.md) bir özeti için her tür değerleri aralığı.  
  
 Tür dönüşümü hakkında daha fazla bilgi için bkz: [standart dönüşümler](../cpp/standard-conversions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri Türü Aralıkları](../cpp/data-type-ranges.md)