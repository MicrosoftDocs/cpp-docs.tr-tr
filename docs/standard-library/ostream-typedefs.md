---
title: '&lt;ostream&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: d0ceae12069712c7a124990d0f81968c21bc683a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419716"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; tür tanımları

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>ostream

Char **üzerinde özelleştirilmiş** basic_ostream, **char**üzerinde özelleştirilmiş `char_traits` bir tür oluşturur.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş [basic_ostream](../standard-library/basic-ostream-class.md)sınıf şablonu için bir eş anlamlı.

## <a name="wostream"></a>wostream

**Wchar_t** ve **wchar_t**üzerinde özelleştirilmiş `char_traits` basic_ostream bir tür oluşturur.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri olan **wchar_t** türündeki öğeler için özelleştirilmiş [basic_ostream](../standard-library/basic-ostream-class.md)sınıf şablonu için bir eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[ostream > \<](../standard-library/ostream.md)
