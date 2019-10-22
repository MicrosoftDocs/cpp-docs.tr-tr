---
title: '&lt;ostream &gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: d0ceae12069712c7a124990d0f81968c21bc683a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687227"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream &gt; tür tanımları

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>ostream

Char **üzerinde özelleştirilmiş ve** **char**üzerinde özelleştirilmiş `char_traits` basic_ostream öğesinden bir tür oluşturur.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş olan sınıf şablonu [basic_ostream](../standard-library/basic-ostream-class.md)için bir eş anlamlıdır.

## <a name="wostream"></a>wostream

**Wchar_t ve** **wchar_t**üzerinde özelleştirilmiş `char_traits` özel basic_ostream öğesinden bir tür oluşturur.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **wchar_t** türü öğeler için özelleştirilmiş olan sınıf şablonu [basic_ostream](../standard-library/basic-ostream-class.md)için bir eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream >](../standard-library/ostream.md)
