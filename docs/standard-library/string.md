---
title: '&lt;dize&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- string/std::<string>
- <string>
dev_langs:
- C++
helpviewer_keywords:
- string header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f915ab0378784b9a8979a422b061c4ef7c155ee6
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltstringgt"></a>&lt;string&gt;

Kapsayıcı Şablon sınıfı tanımlayan `basic_string` ve çeşitli destekleyici şablonları.

Hakkında daha fazla bilgi için `basic_string`, bkz: [basic_string sınıfı](../standard-library/basic-string-class.md)

## <a name="syntax"></a>Sözdizimi

```cpp
#include <string>
```

## <a name="remarks"></a>Açıklamalar

C++ dili ve C++ Standart Kitaplığı iki tür dizeleri destekler:

- Null olarak sonlandırılan bir karakter dizileri genellikle C dize olarak adlandırılır.

- Tür Şablon sınıfı nesneleri `basic_string`, tüm işleyen `char`-bağımsız şablon ister.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[string](../standard-library/string-typedefs.md#string)|Şablon sınıfı uzmanlaşması açıklayan türü `basic_string` türündeki öğeler ile `char` olarak bir `string`.|
|[wstring](../standard-library/string-typedefs.md#wstring)|Şablon sınıfı uzmanlaşması açıklayan türü `basic_string` türündeki öğeler ile `wchar_t` olarak bir `wstring`.|
|[u16string](../standard-library/string-typedefs.md#u16string)|Şablon sınıfı uzmanlaşması açıklayan türü `basic_string` türü öğelere dayanmaktadır `char16_t`.|
|[u32string](../standard-library/string-typedefs.md#u32string)|Şablon sınıfı uzmanlaşması açıklayan türü `basic_string` türü öğelere dayanmaktadır `char32_t`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator +](../standard-library/string-operators.md#op_add)|İki dize nesnelerini art arda ekler.|
|[operator!=](../standard-library/string-operators.md#op_neq)|Dize nesnesi işlecinin sol tarafındaki sağ tarafında dize nesnesi eşit değilse, testleri.|
|[operator==](../standard-library/string-operators.md#op_eq_eq)|Dize nesnesi sağ tarafında işlecinin sol tarafındaki dize nesnesi eşitse testleri.|
|[operator <](../standard-library/string-operators.md#op_lt)|Dize nesnesi işlecinin sol tarafındaki çok kısa ise test sağ tarafında dize nesnesi.|
|[operator < =](../standard-library/string-operators.md#op_lt_eq)|Dize işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında dize nesnesine eşit veya daha az olur.|
|[operator <\<](../standard-library/string-operators.md#op_lt_lt)|Çıkış akışı bir dize ekler şablon işlevi.|
|[operator >](../standard-library/string-operators.md#op_gt)|Dize nesnesi işlecinin sol tarafındaki dize nesnesine sağ tarafında büyükse testleri.|
|[operator>=](../standard-library/string-operators.md#op_gt_eq)|Dize nesnesi işlecinin sol tarafındaki büyük veya ona eşit dize nesnesine sağ tarafında ise testleri.|
|[İşleç >>](../standard-library/string-operators.md#op_gt_gt)|Giriş akışından bir dize ayıklar şablon işlevi.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|||
|-|-|
|[Değiştirme](../standard-library/string-functions.md#swap)|İki dizeyi karakter dizilerine değiş tokuş eder.|
|[stod](../standard-library/string-functions.md#stod)|Bir karakter dizisi dönüştüren bir `double.`|
|[stof](../standard-library/string-functions.md#stof)|Bir karakter dizisi dönüştüren bir `float`.|
|[stoi](../standard-library/string-functions.md#stoi)|Bir karakter dizisi bir tamsayıya dönüştürür.|
|[stold](../standard-library/string-functions.md#stold)|Bir karakter dizisi dönüştüren bir `long double`.|
|[stoll](../standard-library/string-functions.md#stoll)|Bir karakter dizisi dönüştüren bir `long long`.|
|[stoul](../standard-library/string-functions.md#stoul)|Bir karakter dizisi dönüştüren bir `unsigned long`.|
|[stoull](../standard-library/string-functions.md#stoull)|Bir karakter dizisi dönüştüren bir `unsigned long long`.|
|[to_string](../standard-library/string-functions.md#to_string)|Bir değerine dönüştürür bir `string`.|
|[to_wstring](../standard-library/string-functions.md#to_wstring)|Bir geniş bir değeri dönüştürür `string`.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[getline şablonu](../standard-library/string-functions.md#getline)|Dizeleri giriş akışından satır ayıklayın.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_string Sınıfı](../standard-library/basic-string-class.md)|Rasgele karakter benzeri nesneler dizisi depolayabilir açıklayan bir şablon sınıfı nesneleri.|
|[char_traits Yapısı](../standard-library/char-traits-struct.md)|Bir tür CharType karakteri ile ilişkili öznitelikleri açıklanmaktadır bir şablon sınıfı|

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|[char_traits\<char > yapısı](../standard-library/char-traits-char-struct.md)|Şablon yapısı uzmanlığı olan yapı `char_traits` \<CharType > türünde bir öğe için `char`.|
|[char_traits<wchar_t> Yapısı](../standard-library/char-traits-wchar-t-struct.md)|Şablon yapısı uzmanlığı olan yapı `char_traits` \<CharType > türünde bir öğe için `wchar_t`.|
|[char_traits<char16_t> Yapısı](../standard-library/char-traits-char16-t-struct.md)|Şablon yapısı uzmanlığı olan yapı `char_traits` \<CharType > türünde bir öğe için `char16_t`.|
|[char_traits<char32_t> Yapısı](../standard-library/char-traits-char32-t-struct.md)|Şablon yapısı uzmanlığı olan yapı `char_traits` \<CharType > türünde bir öğe için `char32_t`.|

## <a name="requirements"></a>Gereksinimler

- **Başlık:** \<dize >

- **Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
