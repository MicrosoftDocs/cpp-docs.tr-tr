---
title: '&lt;dize&gt; türü tanımları'
ms.date: 11/04/2016
f1_keywords:
- string/std::string
- string/std::u16string
- string/std::u32string
- string/std::wstring
ms.assetid: fdca01e9-f2f1-4b59-abda-0093d760b3cc
ms.openlocfilehash: a1ade5547b98e4376a00f33d45d695a328b772d3
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459230"
---
# <a name="ltstringgt-typedefs"></a>&lt;dize&gt; türü tanımları

||||
|-|-|-|
|[string](#string)|[u16string](#u16string)|[u32string](#u32string)|
|[wstring](#wstring)|

## <a name="string"></a>dizisinde

**Char**türünde öğeleri olan [basic_string](../standard-library/basic-string-class.md) şablon sınıfının bir özelleştirmesi tanımlayan tür.

Özelleştirecek `basic_string` diğer tür tanımları, [wstring](../standard-library/string-typedefs.md#wstring), [u16string](../standard-library/string-typedefs.md#u16string)ve [u32string](../standard-library/string-typedefs.md#u32string)içerir.

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

## <a name="u16string"></a>u16string

Şablon sınıfının [basic_string](../standard-library/basic-string-class.md) türünü `char16_t`içeren bir özelleşmesi tanımlayan tür.

Özelleştirecek `basic_string` diğer tür tanımları [wstring](../standard-library/string-typedefs.md#wstring), [String](../standard-library/string-typedefs.md#string)ve [u32string](../standard-library/string-typedefs.md#u32string)içerir.

```cpp
typedef basic_string<char16_t, char_traits<char16_t>, allocator<char16_t>> u16string;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string"></a>u32string

Şablon sınıfının [basic_string](../standard-library/basic-string-class.md) türünü `char32_t`içeren bir özelleşmesi tanımlayan tür.

Özelleştirecek `basic_string` diğer tür tanımları [String](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string)ve [wstring](../standard-library/string-typedefs.md#wstring)içerir.

```cpp
typedef basic_string<char32_t, char_traits<char32_t>, allocator<char32_t>> u32string;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring"></a>wstring

**Wchar_t**türünde öğeleri olan [basic_string](../standard-library/basic-string-class.md) şablon sınıfının bir özelleştirmesi tanımlayan tür.

Özelleştirecek `basic_string` diğer tür tanımları [String](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string)ve [u32string](../standard-library/string-typedefs.md#u32string)içerir.

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
> **Wchar_t** 'nin boyutu uygulama tanımlı ' dır. Kodunuz **wchar_t** 'yi belirli bir boyut olarak bağımlıysa, platformunuzun uygulamasını (örneğin, ile `sizeof(wchar_t)`) denetleyin. Tüm platformlarda aynı olmaya devam eden bir genişlik içeren bir dize karakter türüne ihtiyacınız varsa, [String](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string)veya [u32string](../standard-library/string-typedefs.md#u32string)kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[\<dize >](../standard-library/string.md)
