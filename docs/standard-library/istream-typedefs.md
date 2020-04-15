---
title: '&lt;istream&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: e9228bddcc3b99503b6b5f0e93b5ed6eeed773d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363091"
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; typedefs

||||
|-|-|-|
|[iostream](#iostream)|[ıstream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a><a name="iostream"></a>Iostream

Char `basic_iostream` konusunda uzmanlaşmış **char**bir tür.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [basic_iostream](../standard-library/basic-iostream-class.md)eşanlamlıdır ve varsayılan karakter özelliklerine sahip **tür char** öğeleri için özelleştirilmiştir.

## <a name="istream"></a><a name="istream"></a>ıstream

Char `basic_istream` konusunda uzmanlaşmış **char**bir tür.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Açıklamalar

Türü sınıf şablonu [basic_istream](../standard-library/basic-istream-class.md)için eşanlamlıdır, varsayılan karakter özellikleri ile tür **char** öğeleri için özel.

## <a name="wiostream"></a><a name="wiostream"></a>wiostream

wchar_t `basic_iostream` konusunda uzmanlaşmış **wchar_t**bir tür.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [basic_iostream](../standard-library/basic-iostream-class.md)eşanlamlıdır ve varsayılan karakter özelliklerine sahip **tür wchar_t** öğeleri için özelleştirilmiştir.

## <a name="wistream"></a><a name="wistream"></a>wistream

wchar_t `basic_istream` konusunda uzmanlaşmış **wchar_t**bir tür.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Açıklamalar

Tür, varsayılan karakter özelliklerine sahip **wchar_t** türü öğeleri için özelleştirilmiş sınıf şablonu [basic_istream](../standard-library/basic-istream-class.md)eşanlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<istream>](../standard-library/istream.md)
