---
title: '&lt;dize&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- string/std::string
- string/std::u16string
- string/std::u32string
- string/std::wstring
ms.assetid: fdca01e9-f2f1-4b59-abda-0093d760b3cc
ms.openlocfilehash: 1ee36d67d137c74e17fff845f9d412b2673f311e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376635"
---
# <a name="ltstringgt-typedefs"></a>&lt;dize&gt; typedefs

||||
|-|-|-|
|[Dize](#string)|[u16string](#u16string)|[u32string](#u32string)|
|[wstring](#wstring)|

## <a name="string"></a><a name="string"></a>Dize

Sınıf [şablonunun](../standard-library/basic-string-class.md) uzmanlık basic_string türü **char**öğeleriyle açıklayan bir tür.

Özelleştirmek diğer typedefs `basic_string` [wstring](../standard-library/string-typedefs.md#wstring)dahil , [u16string](../standard-library/string-typedefs.md#u16string), ve [u32string](../standard-library/string-typedefs.md#u32string).

```cpp
typedef basic_string<char, char_traits<char>, allocator<char>> string;
```

### <a name="remarks"></a>Açıklamalar

Eşdeğer beyanlar şunlardır:

```cpp
string str("");

basic_string<char> str("");
```

Dize oluşturucuların listesi için [bkz: basic_string:basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u16string"></a><a name="u16string"></a>u16string

Sınıf [şablonunun](../standard-library/basic-string-class.md) uzmanlık basic_string tanımlayan bir tür. `char16_t`

Özelleştirmek `basic_string` diğer typedefs [wstring,](../standard-library/string-typedefs.md#wstring) [string](../standard-library/string-typedefs.md#string)ve [u32string](../standard-library/string-typedefs.md#u32string)içerir.

```cpp
typedef basic_string<char16_t, char_traits<char16_t>, allocator<char16_t>> u16string;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucuların listesi için [bkz: basic_string:basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string"></a><a name="u32string"></a>u32string

Sınıf [şablonunun](../standard-library/basic-string-class.md) uzmanlık basic_string tanımlayan bir tür. `char32_t`

Özelleştirmek `basic_string` diğer typedefs [string,](../standard-library/string-typedefs.md#string) [u16string](../standard-library/string-typedefs.md#u16string)ve [wstring](../standard-library/string-typedefs.md#wstring)içerir.

```cpp
typedef basic_string<char32_t, char_traits<char32_t>, allocator<char32_t>> u32string;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucuların listesi için [bkz: basic_string:basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring"></a><a name="wstring"></a>wstring

Sınıf şablonunun uzmanlık wchar_t **türü**öğeleriyle [basic_string](../standard-library/basic-string-class.md) açıklayan bir tür.

Özelleştirmek `basic_string` diğer typedefs [string,](../standard-library/string-typedefs.md#string) [u16string](../standard-library/string-typedefs.md#u16string)ve [u32string](../standard-library/string-typedefs.md#u32string)içerir.

```cpp
typedef basic_string<wchar_t, char_traits<wchar_t>, allocator<wchar_t>> wstring;
```

### <a name="remarks"></a>Açıklamalar

Eşdeğer beyanlar şunlardır:

```cpp
wstring wstr(L"");

basic_string<wchar_t> wstr(L"");
```

Dize oluşturucuların listesi için [bkz: basic_string:basic_string](../standard-library/basic-string-class.md#basic_string).

> [!NOTE]
> **wchar_t** boyutu uygulama tanımlı. Kodunuz **wchar_t** belirli bir boyuta bağlıysa, platformunuzun uygulamasını kontrol `sizeof(wchar_t)`edin (örneğin, ). Tüm platformlarda aynı kalması garanti edilen genişliğe sahip bir dize karakter türüne ihtiyacınız varsa, [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string)veya [u32string](../standard-library/string-typedefs.md#u32string)kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[\<dize>](../standard-library/string.md)
