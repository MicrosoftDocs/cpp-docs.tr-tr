---
title: '&lt;string_view&gt;'
ms.date: 04/18/2019
helpviewer_keywords:
- string_view header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 8952416cf37fc4d8d281d6ced9b8264495ec3799
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346649"
---
# <a name="ltstringviewgt"></a>&lt;string_view&gt;

Sınıf şablonu tanımlar `basic_string_view` ve ilgili türleri ve işleçler. (Derleyici seçeneği gerektirir [Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) veya üzeri.)

## <a name="syntax"></a>Sözdizimi

```cpp
#include <string_view>
```

## <a name="remarks"></a>Açıklamalar

Şablon uzmanlıkları string_view ailesi salt okunur, özel durum açısından güvenli, sahip olmayan bir tanıtıcı sıfır konumunda dizinin ilk öğesi ile herhangi bir dize benzeri nesnelerin karakter verileri geçirmek için etkili bir yol sağlar. Bir işlev parametresi türü `string_view` (için bir typedef olduğu `basic_string_view<char>`) gibi bağımsız değişkenleri kabul edebilir `std::string`, **char\***, veya herhangi bir dize benzeri sınıf olan dar karakter örtük Dönüştürme `string_view` tanımlanır. Benzer şekilde, bir parametre `wstring_view`, `u16string_view` veya `u32string_view` için örtük bir dönüştürme tanımlanan herhangi bir dize türü kabul edebilir. Daha fazla bilgi için [basic_string_view sınıfı](../standard-library/basic-string-view-class.md).

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[string_view](../standard-library/string-view-typedefs.md#string_view)|Sınıf şablonunun bir özelleştirmesi `basic_string_view` öğelerini türle **char**.|
|[wstring_view](../standard-library/string-view-typedefs.md#wstring_view)|Sınıf şablonunun bir özelleştirmesi `basic_string_view` öğelerini türle **wchar_t**.|
|[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)|Sınıf şablonunun bir özelleştirmesi `basic_string_view` öğelerini türle `char16_t`.|
|[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)|Sınıf şablonunun bir özelleştirmesi `basic_string_view` öğelerini türle `char32_t`.|

### <a name="operators"></a>İşleçler

\<String_view > işleçleri karşılaştırabilirsiniz `string_view` nesnelerine dönüştürülebilir tüm nesnelerin dize türleri.

|İşleç|Açıklama|
|-|-|
|[operator!=](../standard-library/string-view-operators.md#op_neq)|İşlecin sol tarafındaki nesne işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.|
|[operator==](../standard-library/string-view-operators.md#op_eq_eq)|İşlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.|
|[işleç <](../standard-library/string-view-operators.md#op_lt)|Nesnesinin işlecin sol tarafındaki küçüktür için olup olmadığını sınar işlecin sağ tarafındaki bir nesne.|
|[operator < =](../standard-library/string-view-operators.md#op_lt_eq)|Nesnesinin işlecin sol tarafındaki küçüktür veya eşittir nesnesinin işlecin sağ tarafındaki olup olmadığını sınar.|
|[işleç <\<](../standard-library/string-view-operators.md#op_lt_lt)|Ekleyen bir şablon işlevine bir `string_view` içine bir çıkış akışı.|
|[operator >](../standard-library/string-view-operators.md#op_gt)|İşlecin sol tarafındaki nesne nesnesine sağ tarafındaki büyük olup olmadığını sınar.|
|[operator>=](../standard-library/string-view-operators.md#op_gt_eq)|İşlecin sol tarafındaki nesnesinin değerinden büyük veya işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.|

### <a name="literals"></a>Sabit değerler

|İşleç|Açıklama|
|-|-|
|[sv](../standard-library/string-view-operators.md#op_sv)|Oluşturur bir `string_view`, `wstring_view`, `u16string_view`, veya `u32string_view` türüne bağlı olarak, eklenmeden dize sabit değeri.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_string_view Sınıfı](../standard-library/basic-string-view-class.md)|Rastgele bir karakter benzeri nesneleri dizisini bir salt okunur görünüm sağlayan bir sınıf şablonunun.|
|[Karma](string-view-hash.md)|Bir string_view için bir karma değer üreten bir işlev nesnesi.|

## <a name="requirements"></a>Gereksinimler

- **Başlık:** \<string_view >

- **Namespace:** std

- **Derleyici seçeneği:** Std: c ++ 17'ı (veya üzeri)

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
