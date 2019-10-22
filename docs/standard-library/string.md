---
title: '&lt;string&gt;'
ms.date: 11/04/2016
f1_keywords:
- string/std::<string>
- <string>
helpviewer_keywords:
- string header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 0b8ca5744418860cc6b4868dda9174ae2eb68a98
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685887"
---
# <a name="ltstringgt"></a>&lt;string&gt;

@No__t_0 kapsayıcı sınıfı şablonunu ve çeşitli destekleyici şablonları tanımlar.

@No__t_0 hakkında daha fazla bilgi için bkz. [basic_string Class](../standard-library/basic-string-class.md)

## <a name="syntax"></a>Sözdizimi

```cpp
#include <string>
```

## <a name="remarks"></a>Açıklamalar

C++ Dil ve C++ standart kitaplık iki tür dizeyi destekler:

- Genellikle C dizeleri olarak adlandırılan null ile sonlandırılmış karakter dizileri.

- Tüm **karakter**benzeri şablon bağımsız değişkenlerini işleyen `basic_string` türündeki sınıf şablonu nesneleri.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[string](../standard-library/string-typedefs.md#string)|Sınıf şablonunun bir özelleştirmesi tanımlayan bir tür, `string` olarak **char** türü öğeleriyle `basic_string`.|
|[wstring](../standard-library/string-typedefs.md#wstring)|Bir `wstring` olarak **wchar_t** türü öğeleriyle `basic_string` sınıf şablonunun bir özelleştirmesi tanımlayan bir tür.|
|[u16string](../standard-library/string-typedefs.md#u16string)|@No__t_1 türündeki öğelere göre `basic_string` sınıf şablonu özelleştirmesi tanımlayan bir tür.|
|[u32string](../standard-library/string-typedefs.md#u32string)|@No__t_1 türündeki öğelere göre `basic_string` sınıf şablonu özelleştirmesi tanımlayan bir tür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç +](../standard-library/string-operators.md#op_add)|İki dize nesnesini birleştirir.|
|[operator!=](../standard-library/string-operators.md#op_neq)|İşlecin sol tarafındaki dize nesnesinin sağ taraftaki dize nesnesine eşit olup olmadığını sınar.|
|[işleç = =](../standard-library/string-operators.md#op_eq_eq)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesine eşit olup olmadığını sınar.|
|[işleç <](../standard-library/string-operators.md#op_lt)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden küçük olup olmadığını sınar.|
|[işleç < =](../standard-library/string-operators.md#op_lt_eq)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden küçük veya ona eşit olup olmadığını sınar.|
|[işleç < \<](../standard-library/string-operators.md#op_lt_lt)|Çıkış akışına bir dize ekleyen bir şablon işlevi.|
|[işleç >](../standard-library/string-operators.md#op_gt)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden büyük olup olmadığını sınar.|
|[operator>=](../standard-library/string-operators.md#op_gt_eq)|İşlecin sol tarafındaki dize nesnesinin, sağ taraftaki dize nesnesinden büyük veya ona eşit olup olmadığını sınar.|
|[işleç > >](../standard-library/string-operators.md#op_gt_gt)|Giriş akışından bir dize çıkaran bir şablon işlevi.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|||
|-|-|
|hash|Bir dizenin karmasını üretir.|
|[Kur](../standard-library/string-functions.md#swap)|İki dizenin karakter dizilerini değiş tokuş eder.|
|[stod](../standard-library/string-functions.md#stod)|Bir karakter dizisini **Double**'a dönüştürür.|
|[stof](../standard-library/string-functions.md#stof)|Bir karakter dizisini **float**öğesine dönüştürür.|
|[Stoi](../standard-library/string-functions.md#stoi)|Bir karakter dizisini tamsayıya dönüştürür.|
|[stold](../standard-library/string-functions.md#stold)|Bir karakter dizisini **Long Double**'a dönüştürür.|
|[Stoll](../standard-library/string-functions.md#stoll)|Bir karakter dizisini **uzun bir uzunluğa**dönüştürür.|
|[stoul](../standard-library/string-functions.md#stoul)|Bir karakter dizisini **işaretsiz bir Long**değerine dönüştürür.|
|[stoull](../standard-library/string-functions.md#stoull)|Bir karakter dizisini **işaretsiz Long**Long değerine dönüştürür.|
|[to_string](../standard-library/string-functions.md#to_string)|Bir değeri `string` dönüştürür.|
|[to_wstring](../standard-library/string-functions.md#to_wstring)|Bir değeri geniş bir `string` dönüştürür.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[getline şablonu](../standard-library/string-functions.md#getline)|Giriş akışı satırından satıra göre dizeleri ayıkla.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_string Sınıfı](../standard-library/basic-string-class.md)|Rastgele karakter benzeri nesneler dizisini depolayabilen nesneleri açıklayan bir sınıf şablonu.|
|[char_traits Yapısı](../standard-library/char-traits-struct.md)|CharType türünde bir karakterle ilişkili öznitelikleri açıklayan bir sınıf şablonu|

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|[char_traits \<char > yapısı](../standard-library/char-traits-char-struct.md)|@No__t_2 türünde bir öğeye > \<CharType `char_traits` şablon yapısına ait bir özelleşmenin bir yapısı.|
|[char_traits<wchar_t> Yapısı](../standard-library/char-traits-wchar-t-struct.md)|@No__t_2 türünde bir öğeye > \<CharType `char_traits` şablon yapısına ait bir özelleşmenin bir yapısı.|
|[char_traits<char16_t> Yapısı](../standard-library/char-traits-char16-t-struct.md)|@No__t_2 türünde bir öğeye > \<CharType `char_traits` şablon yapısına ait bir özelleşmenin bir yapısı.|
|[char_traits<char32_t> Yapısı](../standard-library/char-traits-char32-t-struct.md)|@No__t_2 türünde bir öğeye > \<CharType `char_traits` şablon yapısına ait bir özelleşmenin bir yapısı.|

## <a name="requirements"></a>Gereksinimler

- **Üst bilgi:** \<string >

- **Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
