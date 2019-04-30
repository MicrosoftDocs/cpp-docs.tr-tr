---
title: '&lt;streambuf&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 505739861771a05dd39741f432579a6e9b2d0c26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412390"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; tür tanımları

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a>  streambuf

Bir alt uzmanlaşması `basic_streambuf` kullanan **char** şablon parametreleri olarak.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_streambuf](../standard-library/basic-streambuf-class.md), türü öğeler için özelleştirilmiş **char** varsayılan karakter nitelikleri ile.

## <a name="wstreambuf"></a>  wstreambuf

Bir alt uzmanlaşması `basic_streambuf` kullanan **wchar_t** şablon parametreleri olarak.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_streambuf](../standard-library/basic-streambuf-class.md), türü öğeler için özelleştirilmiş **wchar_t** varsayılan karakter nitelikleri ile.

## <a name="see-also"></a>Ayrıca bkz.

[\<streambuf >](../standard-library/streambuf.md)<br/>
