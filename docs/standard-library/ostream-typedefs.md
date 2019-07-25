---
title: '&lt;ostream&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 18f30a12a6f4d2b97cb5dca3ace98e6241d856a7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447172"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; tür tanımları

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>ostream

Char üzerinde özelleştirilmiş  `char_traits` basic_ostream öğesinden, **char**üzerinde özelleştirilmiş bir tür oluşturur.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş olan şablon sınıfı [basic_ostream](../standard-library/basic-ostream-class.md)için bir eş anlamlıdır.

## <a name="wostream"></a>wostream

**Wchar_t** ve `char_traits` **wchar_t**üzerinde özelleştirilmiş basic_ostream öğesinden bir tür oluşturur.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **wchar_t** türü öğeler için özelleştirilmiş olan şablon sınıfı [basic_ostream](../standard-library/basic-ostream-class.md)için bir eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream >](../standard-library/ostream.md)
