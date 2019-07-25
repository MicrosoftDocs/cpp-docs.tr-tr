---
title: '&lt;string_view&gt; tür tanımları'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: c3367afe1353ac70abb74a59658a255614ac8470
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459176"
---
# <a name="ltstringviewgt-typedefs"></a>&lt;string_view&gt; tür tanımları

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a>string_view

**Char**türünde öğeler içeren [basic_string_view](../standard-library/basic-string-view-class.md) sınıf şablonunun bir özelleştirmesi tanımlayan tür.

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

## <a name="u16string_view"></a>u16string_view

Türü`char16_t`öğeleri olan [basic_string_view](../standard-library/basic-string-view-class.md) sınıf şablonunun bir özelleştirmesi tanımlayan tür.

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string_view"></a>u32string_view

Türü`char32_t`öğeleri olan [basic_string_view](../standard-library/basic-string-view-class.md) sınıf şablonunun bir özelleştirmesi tanımlayan tür.

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring_view"></a>wstring_view

**Wchar_t**türü öğeleriyle [basic_string_view](../standard-library/basic-string-view-class.md) sınıf şablonunun bir özelleştirmesi tanımlayan tür.

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
> **Wchar_t** 'Nin boyutu Windows üzerinde iki bayttır, ancak bu durum tüm platformlar için bu durum değildir. Tüm platformlarda aynı olmaya devam eden bir genişlik ile string_view geniş bir karakter türüne ihtiyacınız varsa, [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) veya [u32string_view](../standard-library/string-view-typedefs.md#u32string_view)kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[\<string_view >](../standard-library/string-view.md)
