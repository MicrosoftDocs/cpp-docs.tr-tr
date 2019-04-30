---
title: '&lt;string_view&gt; tür tanımları'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: 16d7ba49facf24dcffb7df444e445d83d92255e0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346646"
---
# <a name="ltstringviewgt-typedefs"></a>&lt;string_view&gt; tür tanımları

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a> string_view

Sınıf şablonunun bir özelleştirmesi tanımlayan tür [basic_string_view](../standard-library/basic-string-view-class.md) öğelerini türle **char**.

```cpp
typedef basic_string_view<char, char_traits<char>> string_view;
```

### <a name="remarks"></a>Açıklamalar

Eşdeğer bildirimleri aşağıda verilmiştir:

```cpp
string_view str("Hello");

basic_string_view<char> str("Hello");
```

Dize oluşturucular bir listesi için bkz. [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u16string_view"></a> u16string_view

Sınıf şablonunun bir özelleştirmesi tanımlayan tür [basic_string_view](../standard-library/basic-string-view-class.md) öğelerini türle `char16_t`.

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucular bir listesi için bkz. [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string_view"></a> u32string_view

Sınıf şablonunun bir özelleştirmesi tanımlayan tür [basic_string_view](../standard-library/basic-string-view-class.md) öğelerini türle `char32_t`.

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucular bir listesi için bkz. [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring_view"></a>  wstring_view

Sınıf şablonunun bir özelleştirmesi tanımlayan tür [basic_string_view](../standard-library/basic-string-view-class.md) öğelerini türle **wchar_t**.

```cpp
typedef basic_string_view<wchar_t, char_traits<wchar_t>> wstring_view;
```

### <a name="remarks"></a>Açıklamalar

Eşdeğer bildirimleri aşağıda verilmiştir:

```cpp
wstring_view wstr(L"Hello");

basic_string_view<wchar_t> wstr(L"Hello");
```

Dize oluşturucular bir listesi için bkz. [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

> [!NOTE]
> Boyutu **wchar_t** Windows üzerinde iki bayt, ancak bu mutlaka tüm platformlar için geçerli değildir. String_view geniş karakter türü gerekiyorsa tüm platformlarda aynı kalması sağlanır genişliği ile kullanmak [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) veya [u32string_view](../standard-library/string-view-typedefs.md#u32string_view).

## <a name="see-also"></a>Ayrıca bkz.

[\<string_view>](../standard-library/string-view.md)<br/>
