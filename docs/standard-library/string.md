---
title: '&lt;string&gt;'
ms.date: 11/04/2016
f1_keywords:
- string/std::<string>
- <string>
helpviewer_keywords:
- string header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: fda00cd5a8f8768688c8e10f25a0d1f2370a256f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459196"
---
# <a name="ltstringgt"></a>&lt;string&gt;

Kapsayıcı şablonu sınıfını `basic_string` ve çeşitli destekleyici şablonları tanımlar.

Hakkında `basic_string`daha fazla bilgi için bkz. [basic_string Class](../standard-library/basic-string-class.md)

## <a name="syntax"></a>Sözdizimi

```cpp
#include <string>
```

## <a name="remarks"></a>Açıklamalar

C++ Dil ve C++ standart kitaplık iki tür dizeyi destekler:

- Genellikle C dizeleri olarak adlandırılan null ile sonlandırılmış karakter dizileri.

- Tüm char benzeri şablon bağımsız değişkenlerini `basic_string`işleyen türündeki şablon sınıfı nesneleri.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[string](../standard-library/string-typedefs.md#string)|**Char** türünde öğeler içeren bir şablon sınıfının `string` `basic_string` bir özelleştirmesi tanımlayan tür.|
|[wstring](../standard-library/string-typedefs.md#wstring)|`basic_string` **Wchar_t** türü öğeleriyle birlikte şablon sınıfının bir `wstring`özelleştirmesi tanımlayan tür.|
|[u16string](../standard-library/string-typedefs.md#u16string)|`basic_string` Türündeki`char16_t`öğeleri temel alan şablon sınıfının bir özelleştirmesi tanımlayan tür.|
|[u32string](../standard-library/string-typedefs.md#u32string)|`basic_string` Türündeki`char32_t`öğeleri temel alan şablon sınıfının bir özelleştirmesi tanımlayan tür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç +](../standard-library/string-operators.md#op_add)|İki dize nesnesini birleştirir.|
|[operator!=](../standard-library/string-operators.md#op_neq)|İşlecin sol tarafındaki dize nesnesinin sağ taraftaki dize nesnesine eşit olup olmadığını sınar.|
|[operator==](../standard-library/string-operators.md#op_eq_eq)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesine eşit olup olmadığını sınar.|
|[işleç <](../standard-library/string-operators.md#op_lt)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden küçük olup olmadığını sınar.|
|[işleç < =](../standard-library/string-operators.md#op_lt_eq)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden küçük veya ona eşit olup olmadığını sınar.|
|[işleç <\<](../standard-library/string-operators.md#op_lt_lt)|Çıkış akışına bir dize ekleyen bir şablon işlevi.|
|[işleç >](../standard-library/string-operators.md#op_gt)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden büyük olup olmadığını sınar.|
|[operator>=](../standard-library/string-operators.md#op_gt_eq)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden büyük veya ona eşit olup olmadığını sınar.|
|[işleç > >](../standard-library/string-operators.md#op_gt_gt)|Giriş akışından bir dize çıkaran bir şablon işlevi.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|||
|-|-|
|[yla]()||
|[Kur](../standard-library/string-functions.md#swap)|İki dizenin karakter dizilerini değiş tokuş eder.|
|[stod](../standard-library/string-functions.md#stod)|Bir karakter dizisini **Double**'a dönüştürür.|
|[stof](../standard-library/string-functions.md#stof)|Bir karakter dizisini **float**öğesine dönüştürür.|
|[Stoi](../standard-library/string-functions.md#stoi)|Bir karakter dizisini tamsayıya dönüştürür.|
|[stold](../standard-library/string-functions.md#stold)|Bir karakter dizisini **Long Double**'a dönüştürür.|
|[Stoll](../standard-library/string-functions.md#stoll)|Bir karakter dizisini **uzun bir uzunluğa**dönüştürür.|
|[stoul](../standard-library/string-functions.md#stoul)|Bir karakter dizisini **işaretsiz bir Long**değerine dönüştürür.|
|[stoull](../standard-library/string-functions.md#stoull)|Bir karakter dizisini **işaretsiz Long**Long değerine dönüştürür.|
|[to_string](../standard-library/string-functions.md#to_string)|Bir değeri öğesine `string`dönüştürür.|
|[to_wstring](../standard-library/string-functions.md#to_wstring)|Bir değeri geniş `string`bir değere dönüştürür.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[getline şablonu](../standard-library/string-functions.md#getline)|Giriş akışı satırından satıra göre dizeleri ayıkla.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_string Sınıfı](../standard-library/basic-string-class.md)|Rastgele karakter benzeri nesneler dizisini depolayabilen nesneleri tanımlayan bir şablon sınıfı.|
|[char_traits Yapısı](../standard-library/char-traits-struct.md)|CharType türünde bir karakterle ilişkili öznitelikleri açıklayan bir şablon sınıfı|

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|[char_traits\<char > yapısı](../standard-library/char-traits-char-struct.md)|Türündeki \< `char_traits` biröğeye>,CharTypeşablonyapısıözelleştirmesiolanbiryapı.`char`|
|[char_traits<wchar_t> Yapısı](../standard-library/char-traits-wchar-t-struct.md)|Türündeki \< `char_traits` biröğeye>,CharTypeşablonyapısıözelleştirmesiolanbiryapı.`wchar_t`|
|[char_traits<char16_t> Yapısı](../standard-library/char-traits-char16-t-struct.md)|Türündeki \< `char_traits` biröğeye>,CharTypeşablonyapısıözelleştirmesiolanbiryapı.`char16_t`|
|[char_traits<char32_t> Yapısı](../standard-library/char-traits-char32-t-struct.md)|Türündeki \< `char_traits` biröğeye>,CharTypeşablonyapısıözelleştirmesiolanbiryapı.`char32_t`|

## <a name="requirements"></a>Gereksinimler

- **Üst bilgi:** \<dize >

- **Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
