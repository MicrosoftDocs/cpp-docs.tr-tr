---
title: '&lt;string&gt;'
ms.date: 11/04/2016
f1_keywords:
- string/std::<string>
- <string>
helpviewer_keywords:
- string header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 3d84f4707af33f44a930f7f67b7f751e2ead627c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412312"
---
# <a name="ltstringgt"></a>&lt;string&gt;

Kapsayıcı Şablon sınıfı tanımlar `basic_string` ve çeşitli destek şablonları.

Hakkında daha fazla bilgi için `basic_string`, bkz: [basic_string sınıfı](../standard-library/basic-string-class.md)

## <a name="syntax"></a>Sözdizimi

```cpp
#include <string>
```

## <a name="remarks"></a>Açıklamalar

C++ dili ve C++ Standart Kitaplığı dizeleri iki türünü destekler:

- Null ile sonlandırılmış karakter dizileri genellikle C dize olarak adlandırılır.

- Şablon sınıfı, türünden nesnelerin `basic_string`, tüm işleyen **char**-şablon bağımsız değişkenleri ister.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[string](../standard-library/string-typedefs.md#string)|Şablon sınıfı bir alt uzmanlaşması tanımlayan tür `basic_string` öğelerini türle **char** olarak bir `string`.|
|[wstring](../standard-library/string-typedefs.md#wstring)|Şablon sınıfı bir alt uzmanlaşması tanımlayan tür `basic_string` öğelerini türle **wchar_t** olarak bir `wstring`.|
|[u16string](../standard-library/string-typedefs.md#u16string)|Şablon sınıfı bir alt uzmanlaşması tanımlayan tür `basic_string` türünde öğeler `char16_t`.|
|[u32string](../standard-library/string-typedefs.md#u32string)|Şablon sınıfı bir alt uzmanlaşması tanımlayan tür `basic_string` türünde öğeler `char32_t`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator +](../standard-library/string-operators.md#op_add)|İki dize nesnelerinin art arda ekler.|
|[operator!=](../standard-library/string-operators.md#op_neq)|İşlecin sol tarafındaki dize nesnesine sağ tarafındaki dize nesnesine eşit olup olmadığını sınar.|
|[operator==](../standard-library/string-operators.md#op_eq_eq)|İşlecin sol tarafındaki dize nesnesinin işlecin sağ tarafındaki dize nesnesine eşit olup olmadığını sınar.|
|[işleç <](../standard-library/string-operators.md#op_lt)|Dize nesnesinin işlecin sol tarafındaki küçüktür için olup olmadığını sınar işlecin sağ tarafındaki dize nesnesi.|
|[operator < =](../standard-library/string-operators.md#op_lt_eq)|Dize nesnesi işlecinin sol tarafında küçük olup olmadığını sınar veya dize nesnesine eşit işlecin sağ tarafındaki.|
|[işleç <\<](../standard-library/string-operators.md#op_lt_lt)|Bir dize ekler çıkış akışına bir şablon işlevi.|
|[operator >](../standard-library/string-operators.md#op_gt)|İşlecin sol tarafındaki dize nesnesi dize nesnesine sağ tarafındaki büyük olup olmadığını sınar.|
|[operator>=](../standard-library/string-operators.md#op_gt_eq)|İşlecin sol tarafındaki dize nesnesinin değerinden büyük veya işlecin sağ tarafındaki dize nesnesine eşit olup olmadığını sınar.|
|[İşleç >>](../standard-library/string-operators.md#op_gt_gt)|Bir dize girdi akışından ayıklar şablon işlevi.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|||
|-|-|
|[değiştirme](../standard-library/string-functions.md#swap)|İki dizenin karakter dizileri birbiriyle değiştirir.|
|[stod](../standard-library/string-functions.md#stod)|Bir karakter dizisine dönüştürür bir **çift**.|
|[stof](../standard-library/string-functions.md#stof)|Bir karakter dizisine dönüştürür bir **float**.|
|[stoi](../standard-library/string-functions.md#stoi)|Bir karakter dizisine bir tamsayıya dönüştürür.|
|[stold](../standard-library/string-functions.md#stold)|Bir karakter dizisine dönüştürür bir **uzun çift**.|
|[stoll](../standard-library/string-functions.md#stoll)|Bir karakter dizisine dönüştürür bir **uzun uzun**.|
|[stoul](../standard-library/string-functions.md#stoul)|Bir karakter dizisine dönüştürür bir **işaretsiz uzun**.|
|[stoull](../standard-library/string-functions.md#stoull)|Bir karakter dizisine dönüştürür bir **işaretsiz long long**.|
|[to_string](../standard-library/string-functions.md#to_string)|Bir değere dönüştürür bir `string`.|
|[to_wstring](../standard-library/string-functions.md#to_wstring)|Bir değer için bir geniş dönüştürür `string`.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[getline şablonu](../standard-library/string-functions.md#getline)|Dizeleri, giriş akışından satır ayıklayın.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_string Sınıfı](../standard-library/basic-string-class.md)|Tanımlayan bir şablon sınıfı, rastgele bir karakter benzeri nesnelerinin bir dizisi depolayabilirsiniz nesneleri.|
|[char_traits Yapısı](../standard-library/char-traits-struct.md)|CharType türünde bir karakteri ile ilişkili özniteliklerini tanımlayan bir şablon sınıfı|

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|[char_traits\<char > yapısı](../standard-library/char-traits-char-struct.md)|Şablon yapı özelleştirmesi olan yapı `char_traits` \<CharType > türünde bir öğe için `char`.|
|[char_traits<wchar_t> Yapısı](../standard-library/char-traits-wchar-t-struct.md)|Şablon yapı özelleştirmesi olan yapı `char_traits` \<CharType > türünde bir öğe için `wchar_t`.|
|[char_traits<char16_t> Yapısı](../standard-library/char-traits-char16-t-struct.md)|Şablon yapı özelleştirmesi olan yapı `char_traits` \<CharType > türünde bir öğe için `char16_t`.|
|[char_traits<char32_t> Yapısı](../standard-library/char-traits-char32-t-struct.md)|Şablon yapı özelleştirmesi olan yapı `char_traits` \<CharType > türünde bir öğe için `char32_t`.|

## <a name="requirements"></a>Gereksinimler

- **Başlık:** \<dizesi >

- **Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
