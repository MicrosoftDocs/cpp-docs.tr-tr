---
title: '&lt;ostream&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 82539a3fdadf10d340ca957756e235e8ae00b267
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373578"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; typedefs

|||
|-|-|
|[Ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a><a name="ostream"></a>Ostream

**Char** üzerinde uzmanlaşmış ve `char_traits` **char**üzerinde uzmanlaşmış basic_ostream bir tür oluşturur.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Açıklamalar

Türü sınıf şablonu [basic_ostream](../standard-library/basic-ostream-class.md)için eşanlamlıdır , varsayılan karakter özellikleri ile tür **char** öğeleri için özel.

## <a name="wostream"></a><a name="wostream"></a>wostream

**wchar_t** konusunda uzmanlaşmış ve `char_traits` **wchar_t**konusunda uzmanlaşmış basic_ostream bir tür oluşturur.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter özelliklerine sahip tür **wchar_t** öğeleri için özelleştirilmiş sınıf şablonu [basic_ostream](../standard-library/basic-ostream-class.md)eşanlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream>](../standard-library/ostream.md)
