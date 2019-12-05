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
- long keyword [C++]
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
ms.openlocfilehash: 99c30eeb942eb3ab57518cc63ce353cfeff0bec9
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810549"
---
# <a name="fundamental-types--c"></a>Temel Türler (C++)

İçindeki C++ temel türler üç kategoriye ayrılmıştır: integral, kayan nokta ve void. Tam sayı türleri tam sayıları işleme yeteneğine sahiptir. Kayan nokta türleri kesirli parçaları olabilecek değerleri belirtmektir.

[Void](../cpp/void-cpp.md) türü boş bir değer kümesi tanımlar. **Void** türünde bir değişken belirtilemez — birincil olarak değer döndürmeyen işlevleri bildirmek veya türsüz ya da rasgele yazılmış verilere genel işaretçiler bildirmek için kullanılır. Herhangi bir ifade açıkça dönüştürülebilirler veya **void**türüne dönüştürülebilir. Ancak söz konusu ifadelerin aşağıdaki kullanımları kısıtlanmıştır:

- Bir ifade deyimi. (Daha fazla bilgi için bkz. [ifadeler](../cpp/expressions-cpp.md).)

- Virgül işlecinin sol işleneni. (Daha fazla bilgi için bkz. [virgül işleci](../cpp/comma-operator.md) .)

- Koşullu işlecin ikinci veya üçüncü işleneni (`? :`). (Daha fazla bilgi için bkz. [koşullu işlece sahip ifadeler](../cpp/conditional-operator-q.md) .)

Aşağıdaki tabloda tür boyutlarına ilişkin kısıtlamalar açıklanır. Bu sınırlamalar, Microsoft uygulamasından bağımsızdır.

### <a name="fundamental-types-of-the-c-language"></a>C++ Dilinin Temel Türleri

|Kategori|Tür|İçindekiler|
|--------------|----------|--------------|
|Integral|**char**|**Karakter** türü, genellikle temel yürütme karakter kümesinin üyelerini içeren bir integral türüdür; varsayılan olarak bu, MICROSOFT C++içinde ASCII 'dir.<br /><br /> C++ Derleyici **char**, **signed char**ve **işaretsiz char** türündeki değişkenleri farklı türlere sahip olacak şekilde değerlendirir. **Karakter** türündeki değişkenler,/j derleme seçeneği kullanılmadığı sürece varsayılan olarak **imzalanmış char** olarak yazılır gibi **int** 'e yükseltilir. Bu durumda, **imzasız char** türü olarak kabul edilir ve imza uzantısı olmadan **int** 'e yükseltilir.|
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

Aşağıdaki tablo Microsoft C++'da temel türler için gerekli depolama miktarını listeler.

### <a name="sizes-of-fundamental-types"></a>Temel Türlerin Boyutları

|Tür|Boyut|
|----------|----------|
|**bool**, **char**, **işaretsiz karakter**, **işaretli karakter**, **__int8**|1 bayt|
|**__int16**, **kısa**, **işaretsiz kısa**, **wchar_t**, **__wchar_t**|2 bayt|
|**float**, **__int32**, **int**, **işaretsiz int**, **Long**, **unsigned long**|4 bayt|
|**Double**, **__int64**, **Long Double**, **Long Long**|8 bayt|

**SON Microsoft 'a özgü**

Her türün değer aralığının bir özeti için bkz. [veri türü aralıkları](../cpp/data-type-ranges.md) .

Tür dönüştürmesi hakkında daha fazla bilgi için bkz. [Standart dönüştürmeler](../cpp/standard-conversions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Türü Aralıkları](../cpp/data-type-ranges.md)