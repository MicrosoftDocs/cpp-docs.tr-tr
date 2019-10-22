---
title: '&lt;istream &gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: 9a25e4aa9ee42ea36d1bb8d6b196b36ff5c97758
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689485"
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream &gt; tür tanımları

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a>iostream

Bir tür, **char**üzerinde özelleştirilmiş `basic_iostream`.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş olan sınıf şablonu [basic_iostream](../standard-library/basic-iostream-class.md)için bir eş anlamlıdır.

## <a name="istream"></a>istream

Bir tür, **char**üzerinde özelleştirilmiş `basic_istream`.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş olan sınıf şablonu [basic_istream](../standard-library/basic-istream-class.md)için bir eş anlamlıdır.

## <a name="wiostream"></a>wiostream

**Wchar_t**üzerinde özelleştirilmiş bir tür `basic_iostream`.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **wchar_t** türü öğeler için özelleştirilmiş olan sınıf şablonu [basic_iostream](../standard-library/basic-iostream-class.md)için bir eş anlamlıdır.

## <a name="wistream"></a>wistream

**Wchar_t**üzerinde özelleştirilmiş bir tür `basic_istream`.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **wchar_t** türü öğeler için özelleştirilmiş olan sınıf şablonu [basic_istream](../standard-library/basic-istream-class.md)için bir eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<istream >](../standard-library/istream.md)
