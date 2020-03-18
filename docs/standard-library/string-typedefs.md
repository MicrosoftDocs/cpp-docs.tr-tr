---
title: '&lt;dize&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- string/std::string
- string/std::u16string
- string/std::u32string
- string/std::wstring
ms.assetid: fdca01e9-f2f1-4b59-abda-0093d760b3cc
ms.openlocfilehash: 950ca5ae34b6469c3d79b7297d4fe7b7644d2fcf
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419499"
---
# <a name="ltstringgt-typedefs"></a>&lt;dize&gt; tür tanımları

||||
|-|-|-|
|[string](#string)|[u16string](#u16string)|[u32string](#u32string)|
|[wstring](#wstring)|

## <a name="string"></a>dizisinde

Sınıf şablonunun bir özelleştirmesi tanımlayan tür **char**türü öğeleriyle [basic_string](../standard-library/basic-string-class.md) .

`basic_string` özelleştirecek diğer tür tanımları, [wstring](../standard-library/string-typedefs.md#wstring), [u16string](../standard-library/string-typedefs.md#u16string)ve [u32string](../standard-library/string-typedefs.md#u32string)içerir.

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

`char16_t`türündeki öğelerle [basic_string](../standard-library/basic-string-class.md) sınıf şablonunun bir özelleştirmesi tanımlayan bir tür.

`basic_string` özelleştirecek diğer tür tanımları [wstring](../standard-library/string-typedefs.md#wstring), [String](../standard-library/string-typedefs.md#string)ve [u32string](../standard-library/string-typedefs.md#u32string)içerir.

```cpp
typedef basic_string<char16_t, char_traits<char16_t>, allocator<char16_t>> u16string;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string"></a>u32string

`char32_t`türündeki öğelerle [basic_string](../standard-library/basic-string-class.md) sınıf şablonunun bir özelleştirmesi tanımlayan bir tür.

`basic_string` özelleştirecek diğer tür tanımları [String](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string)ve [wstring](../standard-library/string-typedefs.md#wstring)'i içerir.

```cpp
typedef basic_string<char32_t, char_traits<char32_t>, allocator<char32_t>> u32string;
```

### <a name="remarks"></a>Açıklamalar

Dize oluşturucularının bir listesi için bkz. [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring"></a>wstring

**Wchar_t**türündeki öğelerle [basic_string](../standard-library/basic-string-class.md) sınıf şablonunun bir özelleştirmesi tanımlayan bir tür.

Özelleştirme `basic_string` diğer tür tanımları [String](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string)ve [u32string](../standard-library/string-typedefs.md#u32string)' i içerir.

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
> **Wchar_t** boyutu uygulama tanımlı ' dır. Kodunuz belirli bir boyut için **wchar_t** bağımlıysa, platformun uygulamasını (örneğin, `sizeof(wchar_t)`ile) denetleyin. Tüm platformlarda aynı olmaya devam eden bir genişlik içeren bir dize karakter türüne ihtiyacınız varsa, [String](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string)veya [u32string](../standard-library/string-typedefs.md#u32string)kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[\<dize >](../standard-library/string.md)
