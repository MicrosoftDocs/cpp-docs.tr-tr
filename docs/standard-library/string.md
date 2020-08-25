---
title: '&lt;string&gt;'
ms.date: 11/04/2016
f1_keywords:
- string/std::<string>
- <string>
helpviewer_keywords:
- string header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: cb7d869d36bea6854e3eacbacb6dfad0c32a816f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833186"
---
# <a name="ltstringgt"></a>&lt;string&gt;

Kapsayıcı sınıfı şablonunu `basic_string` ve çeşitli destekleyici şablonları tanımlar.

Hakkında daha fazla bilgi için `basic_string` bkz. [basic_string sınıfı](../standard-library/basic-string-class.md)

## <a name="syntax"></a>Syntax

```cpp
#include <string>
```

## <a name="remarks"></a>Açıklamalar

C++ dili ve C++ standart kitaplığı, iki tür dizeyi destekler:

- Genellikle C dizeleri olarak adlandırılan null ile sonlandırılmış karakter dizileri.

- `basic_string`tüm **`char`** benzer şablon bağımsız değişkenlerini işleyen türündeki sınıf şablonu nesneleri.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[dize](../standard-library/string-typedefs.md#string)|`basic_string`Türünde öğeleri olan bir sınıf şablonu özelleştirmesi tanımlayan tür **`char`** `string` .|
|[wstring](../standard-library/string-typedefs.md#wstring)|`basic_string`Türünde öğeleri olan bir sınıf şablonu özelleştirmesi tanımlayan tür **`wchar_t`** `wstring` .|
|[u16string](../standard-library/string-typedefs.md#u16string)|Türündeki öğeleri temel alan sınıf şablonunun bir özelleştirmesi tanımlayan tür `basic_string` **`char16_t`** .|
|[u32string](../standard-library/string-typedefs.md#u32string)|Türündeki öğeleri temel alan sınıf şablonunun bir özelleştirmesi tanımlayan tür `basic_string` **`char32_t`** .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç +](../standard-library/string-operators.md#op_add)|İki dize nesnesini birleştirir.|
|[işleç! =](../standard-library/string-operators.md#op_neq)|İşlecin sol tarafındaki dize nesnesinin sağ taraftaki dize nesnesine eşit olup olmadığını sınar.|
|[işleç = =](../standard-library/string-operators.md#op_eq_eq)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesine eşit olup olmadığını sınar.|
|[işleç<](../standard-library/string-operators.md#op_lt)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden küçük olup olmadığını sınar.|
|[işleç<=](../standard-library/string-operators.md#op_lt_eq)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden küçük veya ona eşit olup olmadığını sınar.|
|[işleç<\<](../standard-library/string-operators.md#op_lt_lt)|Çıkış akışına bir dize ekleyen bir şablon işlevi.|
|[işleç>](../standard-library/string-operators.md#op_gt)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden büyük olup olmadığını sınar.|
|[işleç>=](../standard-library/string-operators.md#op_gt_eq)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden büyük veya ona eşit olup olmadığını sınar.|
|[işleç>>](../standard-library/string-operators.md#op_gt_gt)|Giriş akışından bir dize çıkaran bir şablon işlevi.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Ad|Açıklama|
|-|-|
|`hash`|Bir dizenin karmasını üretir.|
|[Kur](../standard-library/string-functions.md#swap)|İki dizenin karakter dizilerini değiş tokuş eder.|
|[stod](../standard-library/string-functions.md#stod)|Bir karakter dizisini öğesine dönüştürür **`double`** .|
|[stof](../standard-library/string-functions.md#stof)|Bir karakter dizisini öğesine dönüştürür **`float`** .|
|[Stoi](../standard-library/string-functions.md#stoi)|Bir karakter dizisini tamsayıya dönüştürür.|
|[stold](../standard-library/string-functions.md#stold)|Bir karakter dizisini öğesine dönüştürür **`long double`** .|
|[Stoll](../standard-library/string-functions.md#stoll)|Bir karakter dizisini öğesine dönüştürür **`long long`** .|
|[stoul](../standard-library/string-functions.md#stoul)|Bir karakter dizisini bir öğesine dönüştürür **`unsigned long`** .|
|[stoull](../standard-library/string-functions.md#stoull)|Bir karakter dizisini bir öğesine dönüştürür **`unsigned long long`** .|
|[to_string](../standard-library/string-functions.md#to_string)|Bir değeri öğesine dönüştürür `string` .|
|[to_wstring](../standard-library/string-functions.md#to_wstring)|Bir değeri geniş bir değere dönüştürür `string` .|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[getline şablonu](../standard-library/string-functions.md#getline)|Giriş akışı satırından satıra göre dizeleri ayıkla.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[basic_string sınıfı](../standard-library/basic-string-class.md)|Rastgele karakter benzeri nesneler dizisini depolayabilen nesneleri açıklayan bir sınıf şablonu.|
|[char_traits yapısı](../standard-library/char-traits-struct.md)|CharType türünde bir karakterle ilişkili öznitelikleri açıklayan bir sınıf şablonu|

### <a name="specializations"></a>Uzmanlıklar

|Ad|Açıklama|
|-|-|
|[char_traits \<char> yapısı](../standard-library/char-traits-char-struct.md)|Şablon yapısının bir öğesi türünde bir özelleştirmesi olan yapı `char_traits` \<CharType> **`char`** .|
|[char_traits<wchar_t> Yapısı](../standard-library/char-traits-wchar-t-struct.md)|Şablon yapısının bir öğesi türünde bir özelleştirmesi olan yapı `char_traits` \<CharType> **`wchar_t`** .|
|[char_traits<char16_t> Yapısı](../standard-library/char-traits-char16-t-struct.md)|Şablon yapısının bir öğesi türünde bir özelleştirmesi olan yapı `char_traits` \<CharType> **`char16_t`** .|
|[char_traits<char32_t> Yapısı](../standard-library/char-traits-char32-t-struct.md)|Şablon yapısının bir öğesi türünde bir özelleştirmesi olan yapı `char_traits` \<CharType> **`char32_t`** .|

## <a name="requirements"></a>Gereksinimler

- **Üst bilgi:**\<string>

- **Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
