---
title: '&lt;ostream&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 02936fdfc990ea65a99b2875cf7f482eb2ce4ebe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370885"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; tür tanımları

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

Bir tür üzerinde özelleştirilmiş basic_ostream oluşturur **char** ve `char_traits` üzerinde özelleştirilmiş **char**.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_ostream](../standard-library/basic-ostream-class.md), türü öğeler için özelleştirilmiş **char** varsayılan karakter nitelikleri ile.

## <a name="wostream"></a>  wostream

Bir tür üzerinde özelleştirilmiş basic_ostream oluşturur **wchar_t** ve `char_traits` üzerinde özelleştirilmiş **wchar_t**.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için bir eşanlamlı türüdür [basic_ostream](../standard-library/basic-ostream-class.md), türü öğeler için özelleştirilmiş **wchar_t** varsayılan karakter nitelikleri ile.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream >](../standard-library/ostream.md)<br/>
