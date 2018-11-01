---
title: Temel Türler (C++)
ms.date: 11/04/2016
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
ms.openlocfilehash: f4af392ed559349b0e49fd26f3ecb4406a70b74b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601376"
---
# <a name="fundamental-types--c"></a>Temel Türler (C++)

C++ içindeki temel türler üç kategoriye ayrılmıştır: integral, kayan ve void. Tam sayı türleri tam sayıları işleme yeteneğine sahip. Kayan nokta türleri kesirli bölümleri olan değerleri belirtme özelliğine sahiptir.

[Void](../cpp/void-cpp.md) bir boş değer kümesini tanımlayan bir tür. Türünde değişken **void** belirtilebilir — genel işaretçileri yazılmamış veya rastgele yazılmış verilere veya birincil olarak değer döndürmeyen işlevleri bildirmek için kullanılır. Herhangi bir ifade açıkça dönüştürülecek veya türüne yapılan **void**. Ancak, konusu ifadelerin aşağıdaki kullanımları kısıtlanmıştır:

- Bir ifade deyimi. (Bkz [ifadeleri](../cpp/expressions-cpp.md), daha fazla bilgi için.)

- Virgül işlecinin sol işleneni. (Bkz [virgül işleci](../cpp/comma-operator.md) daha fazla bilgi için.)

- Koşullu işlecin ikinci veya üçüncü işleneni (`? :`). (Bkz [koşullu işleç içeren ifadeler](../cpp/conditional-operator-q.md) daha fazla bilgi için.)

Aşağıdaki tabloda tür boyutlarına kısıtlamaları açıklar. Bu kısıtlamalar, Microsoft uygulamasından bağımsızdır.

### <a name="fundamental-types-of-the-c-language"></a>C++ dilinin temel türler

|Kategori|Tür|İçindekiler|
|--------------|----------|--------------|
|tam sayı|**char**|Tür **char** genellikle temel yürütme karakter kümesinin üyelerini içeren bir tamsayı türüdür — varsayılan olarak, Microsoft C++'ta ASCII budur.<br /><br /> C++ derleyicisi türünün değişkenlerine **char**, **signed char**, ve **imzasız char** farklı türlere sahip gibi. Türü değişkenlerindeki **char** yükseltilir **int** türü varsa gibi **signed char** varsayılan olarak, /J derleme seçeneği kullanılmadığı sürece. Bu durumda tür olarak davranılır **imzasız char** ve yükseltilir **int** imza uzantısı olmadan.|
||**bool**|Tür **bool** iki değerden birine sahip olabilir bir tamsayı türüdür **true** veya **false**. Boyutu belirtilmemiş.|
||**short**|Türü **kısa tamsayı** (veya kısaca **kısa**) daha büyük veya ona eşit bir tamsayı türüdür **char**ve daha kısa veya türü boyutunaeşit**int**.<br /><br /> Türündeki nesneler **kısa** olarak bildirilebilir **kısa imzalı** veya **işaretsiz**. **Kısa imzalı** eşanlamlıdır **kısa**.|
||**int**|Tür **int** değerden büyük veya ona eşit bir tamsayı türüdür **kısa tamsayı**ve daha kısa veya ona eşit **uzun**.<br /><br /> Türündeki nesneler **int** olarak bildirilebilir **signed int** veya **işaretsiz int**. **İmzalı int** eşanlamlıdır **int**.|
||**__int8**, **__int16**, **__int32**, **__int64**|Ölçekli tamsayı `__int n`burada `n` tamsayı değişkeninin bit olarak boyutudur. **__int8**, **__int16**, **__int32** ve **__int64** Microsoft'a özgü anahtar sözcükler. Tüm mimarilerde tüm türleri kullanılabilir. (**__int128** desteklenmiyor.)|
||**long**|Tür **uzun** (veya **long int**) daha büyük veya ona eşit bir tamsayı türüdür **int**.<br /><br /> Türündeki nesneler **uzun** olarak bildirilebilir **signed long** veya **işaretsiz uzun**. **Signed long** eşanlamlıdır **uzun**.|
||**Long long**|Büyük bir imzalanmamış **uzun**.<br /><br /> Türündeki nesneler **uzun uzun** olarak bildirilebilir **imzalanmış long long** veya **işaretsiz long long**. **imzalanmış Long long** eşanlamlıdır **uzun uzun**.|
||**wchar_t**, **__wchar_t**|Türünde bir değişken **wchar_t** bir geniş karakter veya çok baytlı karakter türünü belirtir. Varsayılan olarak, **wchar_t** yerel bir tür olduğu halde kullanabileceğiniz [/Zc:wchar_t-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) yapmak **wchar_t** için bir typedef **işaretsiz**. **__Wchar_t** türüdür yerel Microsoft'a özgü eşanlamlısı **wchar_t** türü.<br /><br /> L önekini bir karakter veya dize sabit değeri önce geniş karakter türü belirtmek için kullanın.|
|Kayan nokta|**float**|Tür **float** olan en küçük kayan nokta türüne.|
||**double**|Tür **çift** değerinden daha büyük kayan nokta türünü veya türü için eşittir **float**, ancak daha kısa veya ona eşit **uzun çift**.<br /><br /> Microsoft'a özgü: gösterimini **uzun çift** ve **çift** aynıdır. Ancak, **uzun çift** ve **çift** farklı türlerdir.|
||**uzun çift**|Tür **uzun çift** kayan bir değerinden daha büyük bir nokta türünü ya da türü için eşittir **çift**.|

**Microsoft'a özgü**

Aşağıdaki tablo Microsoft C++'da temel türler için gerekli depolama miktarını listeler.

### <a name="sizes-of-fundamental-types"></a>Temel türlerin boyutları

|Tür|Boyut|
|----------|----------|
|**bool**, **char**, **imzasız char**, **signed char**, **__int8**|1 bayt|
|**__int16**, **kısa**, **işaretsiz**, **wchar_t**, **__wchar_t**|2 bayt|
|**float**, **__int32**, **int**, **işaretsiz int**, **uzun**, **işaretsiz uzun**|4 bayt|
|**çift**, **__int64**, **uzun çift**, **uzun uzun**|8 bayt|

**END Microsoft özgü**

Bkz: [veri türü aralıkları](../cpp/data-type-ranges.md) özeti için her tür değerleri aralığı.

Tür dönüştürme hakkında daha fazla bilgi için bkz: [standart dönüştürmeler](../cpp/standard-conversions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Türü Aralıkları](../cpp/data-type-ranges.md)