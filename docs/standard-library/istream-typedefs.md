---
description: 'Daha fazla bilgi edinin: &lt; IStream &gt; tür tanımları'
title: '&lt;IStream &gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: 576d1be7733a01689b4cfc511049dfad89390f63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277862"
---
# <a name="ltistreamgt-typedefs"></a>&lt;IStream &gt; tür tanımları

[iostream](#iostream)\
[istream](#istream)\
[wiostream](#wiostream)\
[wistream](#wistream)

## <a name="iostream"></a><a name="iostream"></a> iostream

`basic_iostream`Üzerinde özelleştirilmiş bir tür **`char`** .

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-iostream-class.md) **`char`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_iostream sınıf şablonu için bir eş anlamlıdır.

## <a name="istream"></a><a name="istream"></a> istream

`basic_istream`Üzerinde özelleştirilmiş bir tür **`char`** .

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-istream-class.md) **`char`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_istream sınıf şablonu için bir eş anlamlıdır.

## <a name="wiostream"></a><a name="wiostream"></a> wiostream

`basic_iostream`Üzerinde özelleştirilmiş bir tür **`wchar_t`** .

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-iostream-class.md) **`wchar_t`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_iostream sınıf şablonu için bir eş anlamlıdır.

## <a name="wistream"></a><a name="wistream"></a> wistream

`basic_istream`Üzerinde özelleştirilmiş bir tür **`wchar_t`** .

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Açıklamalar

Tür, [](../standard-library/basic-istream-class.md) **`wchar_t`** varsayılan karakter nitelikleri olan türdeki öğeler için özelleştirilmiş basic_istream sınıf şablonu için bir eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<istream>](../standard-library/istream.md)
