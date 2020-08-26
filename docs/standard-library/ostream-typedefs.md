---
title: '&lt;ostream &gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: ff9f19f56c8d8fdb9e469e6361a5419468fe7e67
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846413"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream &gt; tür tanımları

[ostream](#ostream)\
[wostream](#wostream)

## <a name="ostream"></a><a name="ostream"></a> ostream

Üzerinde özelleştirilmiş ve özelleştirilmiş basic_ostream bir tür oluşturur **`char`** `char_traits` **`char`** .

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, [basic_ostream](../standard-library/basic-ostream-class.md) **`char`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_ostream sınıf şablonu için bir eş anlamlıdır.

## <a name="wostream"></a><a name="wostream"></a> wostream

Üzerinde özelleştirilmiş ve özelleştirilmiş basic_ostream bir tür oluşturur **`wchar_t`** `char_traits` **`wchar_t`** .

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, [basic_ostream](../standard-library/basic-ostream-class.md) **`wchar_t`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_ostream sınıf şablonu için bir eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream>](../standard-library/ostream.md)
