---
title: '&lt;streamarabelleğe&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 1c9850ad7d7ec9b9c3554e6806f4790ef3613b08
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866218"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streamarabelleğe&gt; tür tanımları

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a>streambuf

Şablon parametreleri olarak **char** kullanan `basic_streambuf` özelleştirmesi.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş [basic_streambuf](../standard-library/basic-streambuf-class.md)sınıf şablonu için bir eş anladır.

## <a name="wstreambuf"></a>wstreambuf

Şablon parametreleri olarak **wchar_t** kullanan `basic_streambuf` özelleştirmesi.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri olan **wchar_t** türündeki öğeler için özelleştirilmiş [basic_streambuf](../standard-library/basic-streambuf-class.md)sınıf şablonu için bir eş anladır.

## <a name="see-also"></a>Ayrıca bkz.

[\<streamarabelleğe >](../standard-library/streambuf.md)
