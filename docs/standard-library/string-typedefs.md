---
title: '&lt;dize &gt; türü tanımları'
ms.date: 11/04/2016
f1_keywords:
- string/std::string
- string/std::u16string
- string/std::u32string
- string/std::wstring
ms.assetid: fdca01e9-f2f1-4b59-abda-0093d760b3cc
ms.openlocfilehash: 083209f0121ac38d8adf81975577257e4e23a393
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845438"
---
# <a name="ltstringgt-typedefs"></a>&lt;dize &gt; türü tanımları

[dizisinde](#string)\
[u16string](#u16string)\
[u32string](#u32string)\
[wstring](#wstring)

## <a name="string"></a><a name="string"></a> dizisinde

Sınıf şablonunun bir özelleştirmesi tanımlayan tür öğeleri [basic_string](../standard-library/basic-string-class.md) **`char`** .

Özelleştirecek diğer tür tanımları `basic_string` , [wstring](../standard-library/string-typedefs.md#wstring), [u16string](../standard-library/string-typedefs.md#u16string)ve [u32string](../standard-library/string-typedefs.md#u32string)içerir.

```cpp
typedef basic_string<char, char_traits<char>, allocator<char>> string;
```

### <a name="remarks"></a>Açıklamalar

Eşdeğer bildirimler aşağıda verilmiştir:

```cpp
string str("");

basic_string<char> str("");
```

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u16string"></a><a name="u16string"></a> u16string

Sınıf şablonunun bir özelleştirmesi tanımlayan tür öğeleri [basic_string](../standard-library/basic-string-class.md) **`char16_t`** .

Özelleştirecek diğer tür tanımları `basic_string` [wstring](../standard-library/string-typedefs.md#wstring), [String](../standard-library/string-typedefs.md#string)ve [u32string](../standard-library/string-typedefs.md#u32string)içerir.

```cpp
typedef basic_string<char16_t, char_traits<char16_t>, allocator<char16_t>> u16string;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string"></a><a name="u32string"></a> u32string

Sınıf şablonunun bir özelleştirmesi tanımlayan tür öğeleri [basic_string](../standard-library/basic-string-class.md) **`char32_t`** .

Özelleştirecek diğer tür tanımları `basic_string` [String](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string)ve [wstring](../standard-library/string-typedefs.md#wstring)içerir.

```cpp
typedef basic_string<char32_t, char_traits<char32_t>, allocator<char32_t>> u32string;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring"></a><a name="wstring"></a> wstring

Sınıf şablonunun bir özelleştirmesi tanımlayan tür öğeleri [basic_string](../standard-library/basic-string-class.md) **`wchar_t`** .

Özelleştirecek diğer tür tanımları `basic_string` [String](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string)ve [u32string](../standard-library/string-typedefs.md#u32string)içerir.

```cpp
typedef basic_string<wchar_t, char_traits<wchar_t>, allocator<wchar_t>> wstring;
```

### <a name="remarks"></a>Açıklamalar

Eşdeğer bildirimler aşağıda verilmiştir:

```cpp
wstring wstr(L"");

basic_string<wchar_t> wstr(L"");
```

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

> [!NOTE]
> Boyutu **`wchar_t`** uygulama tanımlı ' dır. Kodunuz **`wchar_t`** belirli bir boyut için bağımlıysa, platformun uygulamasını (örneğin, ile `sizeof(wchar_t)` ) denetleyin. Tüm platformlarda aynı olmaya devam eden bir genişlik içeren bir dize karakter türüne ihtiyacınız varsa, [String](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string)veya [u32string](../standard-library/string-typedefs.md#u32string)kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[\<string>](../standard-library/string.md)
