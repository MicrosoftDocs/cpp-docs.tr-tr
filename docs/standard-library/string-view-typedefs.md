---
title: '&lt;string_view&gt; typedefs'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: 0ec278484b7c1c9887771f6cbe7e5d0b05205dd7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376671"
---
# <a name="ltstring_viewgt-typedefs"></a>&lt;string_view&gt; typedefs

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a><a name="string_view"></a>string_view

Sınıf [şablonunun](../standard-library/basic-string-view-class.md) uzmanlık basic_string_view türü **char**öğeleriyle açıklayan bir tür.

```cpp
typedef basic_string_view<char, char_traits<char>> string_view;
```

### <a name="remarks"></a>Açıklamalar

Eşdeğer beyanlar şunlardır:

```cpp
string_view str("Hello");

basic_string_view<char> str("Hello");
```

Dize oluşturucuların listesi için [bkz: basic_string:basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u16string_view"></a><a name="u16string_view"></a>u16string_view

Sınıf [şablonunun](../standard-library/basic-string-view-class.md) uzmanlık basic_string_view türü öğeleriyle açıklayan `char16_t`bir tür.

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucuların listesi için [bkz: basic_string:basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string_view"></a><a name="u32string_view"></a>u32string_view

Sınıf [şablonunun](../standard-library/basic-string-view-class.md) uzmanlık basic_string_view türü öğeleriyle açıklayan `char32_t`bir tür.

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucuların listesi için [bkz: basic_string:basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring_view"></a><a name="wstring_view"></a>wstring_view

Sınıf [şablonunun](../standard-library/basic-string-view-class.md) uzmanlık basic_string_view tür **wchar_t**öğeleriyle açıklayan bir tür.

```cpp
typedef basic_string_view<wchar_t, char_traits<wchar_t>> wstring_view;
```

### <a name="remarks"></a>Açıklamalar

Eşdeğer beyanlar şunlardır:

```cpp
wstring_view wstr(L"Hello");

basic_string_view<wchar_t> wstr(L"Hello");
```

Dize oluşturucuların listesi için [bkz: basic_string:basic_string](../standard-library/basic-string-class.md#basic_string).

> [!NOTE]
> **wchar_t** boyutu Windows'da iki bayt, ancak bu mutlaka tüm platformlar için geçerli değildir. Tüm platformlarda aynı kalması garanti edilen genişliğe sahip string_view geniş karakter türüne ihtiyacınız varsa, [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) veya [u32string_view](../standard-library/string-view-typedefs.md#u32string_view)kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[\<string_view>](../standard-library/string-view.md)
