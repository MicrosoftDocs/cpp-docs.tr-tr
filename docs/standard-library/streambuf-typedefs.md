---
description: 'Daha fazla bilgi edinin: &lt; streamarabelleğe &gt; tür tanımları'
title: '&lt;streamarabelleğe &gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: ae5394213143b05704d452e38eaae0b3581849cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221975"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streamarabelleğe &gt; tür tanımları

[streambuf](#streambuf)\
[wstreambuf](#wstreambuf)

## <a name="streambuf"></a><a name="streambuf"></a> streambuf

`basic_streambuf` **`char`** Şablon parametreleri olarak kullanılan özelleştirmesi.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-streambuf-class.md) **`char`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_streambuf sınıf şablonu için bir eş anlamlıdır.

## <a name="wstreambuf"></a><a name="wstreambuf"></a> wstreambuf

`basic_streambuf` **`wchar_t`** Şablon parametreleri olarak kullanılan özelleştirmesi.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-streambuf-class.md) **`wchar_t`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_streambuf sınıf şablonu için bir eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<streambuf>](../standard-library/streambuf.md)
