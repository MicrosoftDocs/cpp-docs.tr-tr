---
title: '&lt;string_view&gt;'
ms.date: 04/18/2019
helpviewer_keywords:
- string_view header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 47924c3d6bd1a2f45cdbac648f4f563c57ce8939
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459113"
---
# <a name="ltstringviewgt"></a>&lt;string_view&gt;

Sınıf şablonunu `basic_string_view` ve ilgili türleri ve işleçleri tanımlar. (Bir derleyici seçeneği [std: c++ 17](../build/reference/std-specify-language-standard-version.md) veya sonraki bir sürümü gerektirir.)

## <a name="syntax"></a>Sözdizimi

```cpp
#include <string_view>
```

## <a name="remarks"></a>Açıklamalar

Şablon Uzmanlıkları string_view ailesi, salt okunurdur, özel durum güvenli, sahip olmayan bir tutamacı, dizinin ilk öğesi olan herhangi bir dize benzeri nesnenin karakter verilerine geçirmek için etkili bir yol sağlar. Türünde `string_view` bir işlev parametresi (için `basic_string_view<char>`bir typedef) `std::string`, bir örtük dönüştürme **\*** `string_view`işlemiiçin,charveyadarkarakterlerdenoluşandiğerdizebenzeribağımsızdeğişkenlerikabuledebilirtanımlanmıştır. Benzer şekilde, `wstring_view` `u16string_view` veya `u32string_view` parametresi örtük bir dönüştürme tanımlanmış herhangi bir dize türünü kabul edebilir. Daha fazla bilgi için bkz. [Basic_string_view Class](../standard-library/basic-string-view-class.md).

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[string_view](../standard-library/string-view-typedefs.md#string_view)|**Char**türünde öğeler içeren sınıf şablonunun `basic_string_view` özelleştirmesi.|
|[wstring_view](../standard-library/string-view-typedefs.md#wstring_view)|**Wchar_t**türünde öğeler içeren sınıf şablonunun `basic_string_view` özelleştirmesi.|
|[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)|`basic_string_view` Türünde`char16_t`öğeler içeren sınıf şablonunun özelleştirmesi.|
|[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)|`basic_string_view` Türünde`char32_t`öğeler içeren sınıf şablonunun özelleştirmesi.|

### <a name="operators"></a>İşleçler

String_view > işleçleri nesneleri herhangi bir dönüştürülebilir dize türünün nesneleriyle karşılaştırabilirler `string_view`. \<

|İşleç|Açıklama|
|-|-|
|[operator!=](../standard-library/string-view-operators.md#op_neq)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.|
|[operator==](../standard-library/string-view-operators.md#op_eq_eq)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.|
|[işleç <](../standard-library/string-view-operators.md#op_lt)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden daha az olup olmadığını sınar.|
|[işleç < =](../standard-library/string-view-operators.md#op_lt_eq)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden küçük veya ona eşit olup olmadığını sınar.|
|[işleç <\<](../standard-library/string-view-operators.md#op_lt_lt)|Bir çıkış akışına bir `string_view` ekleyen bir şablon işlevi.|
|[işleç >](../standard-library/string-view-operators.md#op_gt)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden daha büyük olup olmadığını sınar.|
|[operator>=](../standard-library/string-view-operators.md#op_gt_eq)|İşlecin sol tarafındaki nesnenin sağ taraftaki nesneden büyük veya ona eşit olup olmadığını sınar.|

### <a name="literals"></a>Sabit değerler

|İşleç|Açıklama|
|-|-|
|[v](../standard-library/string-view-operators.md#op_sv)|Eklendiği dize sabit değerinin türüne bağlı `u32string_view` olarak,, veya oluşturur. `string_view` `wstring_view` `u16string_view`|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_string_view Sınıfı](../standard-library/basic-string-view-class.md)|Rastgele bir karakter benzeri nesne dizisine salt okunurdur görünümü sağlayan bir sınıf şablonu.|
|[yla](string-view-hash.md)|Bir string_view için karma değer üreten işlev nesnesi.|

## <a name="requirements"></a>Gereksinimler

- **Üst bilgi:** \<string_view >

- **Ad alanı:** std

- **Derleyici seçeneği:** std: c++ 17 (veya üzeri)

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
