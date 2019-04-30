---
title: '&lt;dize&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- string/std::string
- string/std::u16string
- string/std::u32string
- string/std::wstring
ms.assetid: fdca01e9-f2f1-4b59-abda-0093d760b3cc
ms.openlocfilehash: 534c51e8a627ca893ea42e023f12d8bc62d6fb5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412338"
---
# <a name="ltstringgt-typedefs"></a>&lt;dize&gt; tür tanımları

||||
|-|-|-|
|[string](#string)|[u16string](#u16string)|[u32string](#u32string)|
|[wstring](#wstring)|

## <a name="string"></a>  dize

Şablon sınıfı bir alt uzmanlaşması tanımlayan tür [basic_string](../standard-library/basic-string-class.md) öğelerini türle **char**.

Specialize diğer tür tanımları `basic_string` dahil [wstring](../standard-library/string-typedefs.md#wstring), [u16string](../standard-library/string-typedefs.md#u16string), ve [u32string](../standard-library/string-typedefs.md#u32string).

```cpp
typedef basic_string<char, char_traits<char>, allocator<char>> string;
```

### <a name="remarks"></a>Açıklamalar

Eşdeğer bildirimleri aşağıda verilmiştir:

```cpp
string str("");

basic_string<char> str("");
```

Dize oluşturucular bir listesi için bkz. [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u16string"></a>  u16string

Şablon sınıfı bir alt uzmanlaşması tanımlayan tür [basic_string](../standard-library/basic-string-class.md) öğelerini türle `char16_t`.

Specialize diğer tür tanımları `basic_string` dahil [wstring](../standard-library/string-typedefs.md#wstring), [dize](../standard-library/string-typedefs.md#string), ve [u32string](../standard-library/string-typedefs.md#u32string).

```cpp
typedef basic_string<char16_t, char_traits<char16_t>, allocator<char16_t>> u16string;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucular bir listesi için bkz. [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string"></a>  u32string

Şablon sınıfı bir alt uzmanlaşması tanımlayan tür [basic_string](../standard-library/basic-string-class.md) öğelerini türle `char32_t`.

Specialize diğer tür tanımları `basic_string` dahil [dize](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string), ve [wstring](../standard-library/string-typedefs.md#wstring).

```cpp
typedef basic_string<char32_t, char_traits<char32_t>, allocator<char32_t>> u32string;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucular bir listesi için bkz. [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring"></a>  wstring

Şablon sınıfı bir alt uzmanlaşması tanımlayan tür [basic_string](../standard-library/basic-string-class.md) öğelerini türle **wchar_t**.

Specialize diğer tür tanımları `basic_string` dahil [dize](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string), ve [u32string](../standard-library/string-typedefs.md#u32string).

```cpp
typedef basic_string<wchar_t, char_traits<wchar_t>, allocator<wchar_t>> wstring;
```

### <a name="remarks"></a>Açıklamalar

Eşdeğer bildirimleri aşağıda verilmiştir:

```cpp
wstring wstr(L"");

basic_string<wchar_t> wstr(L"");
```

Dize oluşturucular bir listesi için bkz. [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

> [!NOTE]
> Boyutu **wchar_t** uygulama tarafından tanımlanır. Kodunuzu yapılandırmasanız **wchar_t** , platformun uygulama belirli bir boyutu denetleyin (örneğin, `sizeof(wchar_t)`). Bir dizeyi karakter türü gerekiyorsa tüm platformlarda aynı kalması sağlanır genişliği ile kullanmak [dize](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string), veya [u32string](../standard-library/string-typedefs.md#u32string).

## <a name="see-also"></a>Ayrıca bkz.

[\<dize >](../standard-library/string.md)<br/>
