---
description: 'Daha fazla bilgi edinin: &lt; ostream &gt; tür tanımları'
title: '&lt;ostream &gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 886fb729f389fac161e4d154e00898b530d1d9f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193025"
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

Tür, [](../standard-library/basic-ostream-class.md) **`char`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_ostream sınıf şablonu için bir eş anlamlıdır.

## <a name="wostream"></a><a name="wostream"></a> wostream

Üzerinde özelleştirilmiş ve özelleştirilmiş basic_ostream bir tür oluşturur **`wchar_t`** `char_traits` **`wchar_t`** .

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-ostream-class.md) **`wchar_t`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_ostream sınıf şablonu için bir eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream>](../standard-library/ostream.md)
