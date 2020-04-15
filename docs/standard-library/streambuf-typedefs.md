---
title: '&lt;streambuf&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 8eb058f161a9f30ccf5e9d49307b50c215f79c22
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376690"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; typedefs

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a><a name="streambuf"></a>streambuf

Bunun bir `basic_streambuf` uzmanlık şablon parametreleri olarak **char** kullanır.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [basic_streambuf](../standard-library/basic-streambuf-class.md)eşanlamlıdır, varsayılan karakter özellikleri ile tür **char** öğeleri için özel.

## <a name="wstreambuf"></a><a name="wstreambuf"></a>wstreambuf

Şablon parametreleri `basic_streambuf` olarak **wchar_t** kullanır bu uzmanlık.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter özelliklerine sahip **wchar_t** türü öğeleri için özelleştirilmiş sınıf şablonu [basic_streambuf](../standard-library/basic-streambuf-class.md)eşanlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<streambuf>](../standard-library/streambuf.md)
