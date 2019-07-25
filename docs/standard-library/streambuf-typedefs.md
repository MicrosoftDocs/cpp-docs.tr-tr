---
title: '&lt;streamarabelleğe&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 178b489d92a4ed7340084490329fdf8fa16c2aa7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449583"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streamarabelleğe&gt; tür tanımları

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a>streambuf

Şablon parametreleri olarak `basic_streambuf` **char** kullanan bir özelleştirmesi.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş olan [basic_streambuf](../standard-library/basic-streambuf-class.md)şablon sınıfının bir eş anlamlısıdır.

## <a name="wstreambuf"></a>wstreambuf

Şablon parametreleri olarak `basic_streambuf` **wchar_t** 'yi kullanan bir özelleştirmesi.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **wchar_t** türü öğeler için özelleştirilmiş olan [basic_streambuf](../standard-library/basic-streambuf-class.md)şablon sınıfının bir eş anlamlısıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<streamarabelleğe >](../standard-library/streambuf.md)
