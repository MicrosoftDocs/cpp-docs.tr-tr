---
title: Yerleşik türler (C++)
ms.date: 12/11/2019
f1_keywords:
- __int128_cpp
- __wchar_t_cpp
- char_cpp
- char8_t_cpp
- char16_t_cpp
- char32_t_cpp
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
- long keyword [C++]
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
ms.openlocfilehash: e67d31e18ebbb6afd9d98542e4a6aa236b2d3e71
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445315"
---
# <a name="built-in-types-c"></a>Yerleşik türler (C++)

Yerleşik türler ( *temel türler*de denir) C++ dil standardı tarafından belirtilir ve derleyicide yerleşik olarak bulunur. Yerleşik türler herhangi bir başlık dosyasında tanımlı değil. Yerleşik türler üç kategoriye ayrılmıştır: integral, kayan nokta ve void. Integral türleri tam sayıları işleyebilir. Kayan nokta türleri kesirli parçaları olabilecek değerleri belirtmektir.

[Void](void-cpp.md) türü boş bir değer kümesi tanımlar. **Void** türünde bir değişken belirtilemez — birincil olarak değer döndürmeyen işlevleri bildirmek veya türsüz ya da rasgele yazılmış verilere genel işaretçiler bildirmek için kullanılır. Herhangi bir ifade açıkça dönüştürülebilirler veya **void**türüne dönüştürülebilir. Ancak, bu tür ifadeler aşağıdaki kullanımlar ile kısıtlıdır:

- Bir ifade deyimi. (Daha fazla bilgi için bkz. [ifadeler](expressions-cpp.md).)

- Virgül işlecinin sol işleneni. (Daha fazla bilgi için bkz. [virgül işleci](comma-operator.md).)

- Koşullu işlecin ikinci veya üçüncü işleneni (`? :`). (Daha fazla bilgi için bkz. [koşullu işlece sahip ifadeler](conditional-operator-q.md).)

Aşağıdaki tabloda, bir birbirleriyle bağlantılı olarak tür boyutlarıyla ilgili kısıtlamalar açıklanmaktadır. Bu kısıtlamalar C++ standart tarafından uygulanan ve Microsoft uygulamasından bağımsızdır. Belirli yerleşik türlerin mutlak boyutu standart olarak belirtilmez.

### <a name="built-in-type-size-restrictions"></a>Yerleşik tür boyutu kısıtlamaları

|Kategori|Tür|İçindekiler|
|--------------|----------|--------------|
|Tam|**char**|**Karakter** türü, genellikle temel yürütme karakter kümesinin üyelerini içeren bir integral türüdür; varsayılan olarak bu, MICROSOFT C++içinde ASCII 'dir.<br /><br /> C++ Derleyici **char**, **signed char**ve **işaretsiz char** türündeki değişkenleri farklı türlere sahip olacak şekilde değerlendirir. **Karakter** türündeki değişkenler,/j derleme seçeneği kullanılmadığı sürece varsayılan olarak **imzalanmış char** olarak yazılır gibi **int** 'e yükseltilir. Bu durumda, **imzasız karakter** türü olarak değerlendirilir ve imza uzantısı olmadan **int** 'e yükseltilir.|
||**bool**|**Bool** türü iki değerden biri **true** veya **false**olan bir integral türüdür. Boyutu belirtilmemiş.|
||**short**|**Short tamsayı** (veya kısaca **Short**) türü, **char**türünden büyük veya ona eşit olan bir tamsayı türüdür ve **int**türünden daha kısa veya ona eşittir.<br /><br /> **Short** türündeki nesneler, **imzalanmış Short** veya **işaretsiz kısa**olarak bildirilemez. **İmzalanan kısa** , **kısa**bir eşanlamlıdır.|
||**int**|**İnt** türü, **kısa tamsayı**türünden daha büyük veya ona eşit olan bir tamsayı türüdür ve **Long**türünden daha kısa veya ona eşittir.<br /><br /> **İnt** türündeki nesneler, **imzalanan int** veya **işaretsiz int**olarak bildirilemez. **İmzalanan int** , **int**için bir eş anladır.|
||**__int8**, **__int16**, **__int32**, **__int64**|Boyutlu tamsayı `__int n`, burada `n` tamsayı değişkeninin bit cinsinden boyutudur. **__int8**, **__int16**, **__int32** ve **__int64** , Microsoft 'a özgü anahtar sözcüklerdir. Tüm mimarilerde tüm türler kullanılamaz. ( **__int128** desteklenmez.)|
||**long**|**Long** (veya **long int**) türü, **int**türünden büyük veya ona eşit olan bir tamsayı türüdür. (Windows **Long** üzerinde **int**ile aynı boyutta olur.)<br /><br /> **Long** türündeki nesneler, **imzalanmış Long** veya **unsigned long**olarak bildirilemez. **İmzalanan Long** , **Long**için bir eş anlamlı.|
||**uzun uzun**|İşaretsiz bir **Long**değerinden büyük.<br /><br /> **Uzun uzun** nesne türündeki nesneler, **imzalanmış Long** Long veya **unsigned**Long Long olarak bildirilemez. **imzalanan uzun** Long **uzun**uzun bir eş anlamlı.|
||**wchar_t**, **__wchar_t**|**Wchar_t** türünde bir değişken, geniş karakter veya çok baytlı karakter türü belirler. Varsayılan olarak, **wchar_t** yerel bir türdür, ancak bir typedef **wchar_t** **işaretsiz Short**için [wchar_t/Zc:](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) kullanabilirsiniz. **__Wchar_t** türü yerel **wchar_t** türü için Microsoft 'a özgü bir eş anlamlıdır.<br /><br /> Geniş karakterli türü belirlemek için bir karakter veya dize sabiti öncesinde L önekini kullanın.|
|Kayan nokta|**float**|**Float** türü en küçük kayan nokta türüdür.|
||**double**|**Double** türü, **float**türünden büyük veya buna eşit olan, ancak **Long Double**türündeki boyuttan daha kısa veya eşit olan bir kayan nokta türüdür.<br /><br /> Microsoft 'a özgü: **Long Double** ve **Double** gösterimi özdeş. Ancak, **Long Double** ve **Double** ayrı türlerdir.|
||**uzun çift**|**Long Double** türü **Double**türünden büyük veya buna eşit bir kayan nokta türüdür.|

**Microsoft 'a özgü**

Aşağıdaki tabloda, Microsoft C++'taki yerleşik türler için gereken depolama alanı miktarı listelenmektedir. Özellikle, 64 bitlik işletim sistemlerinde bile 4 **bayt olduğunu unutmayın** .

### <a name="sizes-of-built-in-types"></a>Yerleşik türlerin boyutları

|Tür|Boyut|
|----------|----------|
|**bool**, **char**, **işaretsiz karakter**, **işaretli karakter**, **__int8**|1 bayt|
|**__int16**, **kısa**, **işaretsiz kısa**, **wchar_t**, **__wchar_t**|2 bayt|
|**float**, **__int32**, **int**, **işaretsiz int**, **Long**, **unsigned long**|4 bayt|
|**Double**, **__int64**, **Long Double**, **Long Long**|8 bayt|

**SON Microsoft 'a özgü**

Her türün değer aralığının bir özeti için bkz. [veri türü aralıkları](data-type-ranges.md) .

Tür dönüştürmesi hakkında daha fazla bilgi için bkz. [Standart dönüştürmeler](standard-conversions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Türü Aralıkları](data-type-ranges.md)