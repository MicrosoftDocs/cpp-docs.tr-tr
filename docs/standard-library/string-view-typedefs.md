---
description: 'Hakkında daha fazla bilgi edinin: &lt; string_view &gt; tür tanımları'
title: '&lt;string_view &gt; tür tanımları'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: 8bef37a85469dbc076c3488b1c70b394e5c63915
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183653"
---
# <a name="ltstring_viewgt-typedefs"></a>&lt;string_view &gt; tür tanımları

[string_view](#string_view)\
[u16string_view](#u16string_view)\
[u32string_view](#u32string_view)\
[wstring_view](#wstring_view)

## <a name="string_view"></a><a name="string_view"></a> string_view

Sınıf şablonunun bir özelleştirmesi tanımlayan tür öğeleri [basic_string_view](../standard-library/basic-string-view-class.md) **`char`** .

```cpp
typedef basic_string_view<char, char_traits<char>> string_view;
```

### <a name="remarks"></a>Açıklamalar

Eşdeğer bildirimler aşağıda verilmiştir:

```cpp
string_view str("Hello");

basic_string_view<char> str("Hello");
```

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u16string_view"></a><a name="u16string_view"></a> u16string_view

Sınıf şablonunun bir özelleştirmesi tanımlayan tür öğeleri [basic_string_view](../standard-library/basic-string-view-class.md) **`char16_t`** .

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string_view"></a><a name="u32string_view"></a> u32string_view

Sınıf şablonunun bir özelleştirmesi tanımlayan tür öğeleri [basic_string_view](../standard-library/basic-string-view-class.md) **`char32_t`** .

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring_view"></a><a name="wstring_view"></a> wstring_view

Sınıf şablonunun bir özelleştirmesi tanımlayan tür öğeleri [basic_string_view](../standard-library/basic-string-view-class.md) **`wchar_t`** .

```cpp
typedef basic_string_view<wchar_t, char_traits<wchar_t>> wstring_view;
```

### <a name="remarks"></a>Açıklamalar

Eşdeğer bildirimler aşağıda verilmiştir:

```cpp
wstring_view wstr(L"Hello");

basic_string_view<wchar_t> wstr(L"Hello");
```

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

> [!NOTE]
> Boyutu **`wchar_t`** Windows üzerinde iki bayttır, ancak bu durum tüm platformlar için bu durum değildir. Tüm platformlarda aynı olmaya devam eden bir genişliği olan string_view geniş bir karakter türüne ihtiyacınız varsa [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) veya [u32string_view](../standard-library/string-view-typedefs.md#u32string_view)kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[\<string_view>](../standard-library/string-view.md)
