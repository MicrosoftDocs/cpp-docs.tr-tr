---
title: '&lt;string_view&gt;'
ms.date: 04/18/2019
helpviewer_keywords:
- string_view header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 13b6f5c63b9426fc4c31527f0d1ae8291d07807f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222218"
---
# <a name="ltstring_viewgt"></a>&lt;string_view&gt;

Sınıf şablonunu `basic_string_view` ve ilgili türleri ve işleçleri tanımlar. (Bir derleyici seçeneği [std: c++ 17](../build/reference/std-specify-language-standard-version.md) veya sonraki bir sürümü gerektirir.)

## <a name="syntax"></a>Sözdizimi

```cpp
#include <string_view>
```

## <a name="remarks"></a>Açıklamalar

Şablon Uzmanlıkları string_view Aile, salt okunurdur, özel durum güvenli, sahip olmayan bir tutamacı, dizinin ilk öğesi olan herhangi bir dize benzeri nesnenin karakter verilerine geçirmek için etkili bir yol sağlar. Türünde bir işlev parametresi `string_view` (için bir typedef `basic_string_view<char>` ) `std::string` , bir örtük dönüştürmenin tanımlandığı, **char \* **veya dar karakterlerin diğer dize benzeri bir sınıfı gibi bağımsız değişkenleri kabul edebilir `string_view` . Benzer şekilde, veya parametresi `wstring_view` `u16string_view` örtük bir `u32string_view` dönüştürme tanımlanmış herhangi bir dize türünü kabul edebilir. Daha fazla bilgi için bkz. [Basic_string_view sınıfı](../standard-library/basic-string-view-class.md).

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[string_view](../standard-library/string-view-typedefs.md#string_view)|Türünde öğeler içeren sınıf şablonunun özelleştirmesi `basic_string_view` **`char`** .|
|[wstring_view](../standard-library/string-view-typedefs.md#wstring_view)|Türünde öğeler içeren sınıf şablonunun özelleştirmesi `basic_string_view` **`wchar_t`** .|
|[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)|Türünde öğeler içeren sınıf şablonunun özelleştirmesi `basic_string_view` **`char16_t`** .|
|[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)|Türünde öğeler içeren sınıf şablonunun özelleştirmesi `basic_string_view` **`char32_t`** .|

### <a name="operators"></a>İşleçler

\<string_view>İşleçler `string_view` nesneleri herhangi bir dönüştürülebilir dize türünün nesneleriyle karşılaştırabilirler.

|İşleç|Açıklama|
|-|-|
|[işleç! =](../standard-library/string-view-operators.md#op_neq)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.|
|[işleç = =](../standard-library/string-view-operators.md#op_eq_eq)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.|
|[işleç<](../standard-library/string-view-operators.md#op_lt)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden daha az olup olmadığını sınar.|
|[işleç<=](../standard-library/string-view-operators.md#op_lt_eq)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden küçük veya ona eşit olup olmadığını sınar.|
|[işleç<\<](../standard-library/string-view-operators.md#op_lt_lt)|Bir çıkış akışına bir ekleyen bir şablon işlevi `string_view` .|
|[işleç>](../standard-library/string-view-operators.md#op_gt)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden daha büyük olup olmadığını sınar.|
|[işleç>=](../standard-library/string-view-operators.md#op_gt_eq)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden büyük veya ona eşit olup olmadığını sınar.|

### <a name="literals"></a>Değişmez Değerler

|İşleç|Açıklama|
|-|-|
|[v](../standard-library/string-view-operators.md#op_sv)|Eklendiği `string_view` `wstring_view` `u16string_view` `u32string_view` dize sabit değerinin türüne bağlı olarak,, veya oluşturur.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[basic_string_view sınıfı](../standard-library/basic-string-view-class.md)|Rastgele bir karakter benzeri nesne dizisine salt okunurdur görünümü sağlayan bir sınıf şablonu.|
|[yla](string-view-hash.md)|String_view için bir karma değer üreten işlev nesnesi.|

## <a name="requirements"></a>Gereksinimler

- **Üst bilgi:**\<string_view>

- **Ad alanı:** std

- **Derleyici seçeneği:** std: c++ 17 (veya üzeri)

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
