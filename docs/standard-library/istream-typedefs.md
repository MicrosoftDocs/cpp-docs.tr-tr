---
title: '&lt;IStream&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: 864854fa2697a76c2f3476bcb050d5f5d084dc9d
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458755"
---
# <a name="ltistreamgt-typedefs"></a>&lt;IStream&gt; tür tanımları

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a>iostream

Char üzerinde `basic_iostream` özelleştirilmiş bir tür.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş olan şablon sınıfı [basic_iostream](../standard-library/basic-iostream-class.md)için bir eş anlamlıdır.

## <a name="istream"></a>istream

Char üzerinde `basic_istream` özelleştirilmiş bir tür.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **char** türündeki öğeler için özelleştirilmiş olan şablon sınıfı [basic_istream](../standard-library/basic-istream-class.md)için bir eş anlamlıdır.

## <a name="wiostream"></a>wiostream

Wchar_t üzerinde `basic_iostream` özelleştirilmiş bir tür.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **wchar_t** türü öğeler için özelleştirilmiş olan şablon sınıfı [basic_iostream](../standard-library/basic-iostream-class.md)için bir eş anlamlıdır.

## <a name="wistream"></a>wistream

Wchar_t üzerinde `basic_istream` özelleştirilmiş bir tür.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter nitelikleri ile **wchar_t** türü öğeler için özelleştirilmiş olan şablon sınıfı [basic_istream](../standard-library/basic-istream-class.md)için bir eş anlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<IStream >](../standard-library/istream.md)
