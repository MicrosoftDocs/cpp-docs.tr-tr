---
title: '&lt;istream&gt; tür tanımları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
caps.latest.revision: 10
manager: ghogen
ms.openlocfilehash: 0c27a5fcb3efab861b2f7da4ea4a5fdf978bbbb1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; tür tanımları

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a>  iostream

Bir tür `basic_iostream` üzerinde özel `char`.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için eş anlamlı türüdür [basic_iostream](../standard-library/basic-iostream-class.md), türündeki öğeler için özelleştirilmiş `char` varsayılan karakter nitelikler ile.

## <a name="istream"></a>  istream

Bir tür `basic_istream` üzerinde özel `char`.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için eş anlamlı türüdür [basic_istream](../standard-library/basic-istream-class.md), türündeki öğeler için özelleştirilmiş `char` varsayılan karakter nitelikler ile.

## <a name="wiostream"></a>  wiostream

Bir tür `basic_iostream` üzerinde özel `wchar_t`.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için eş anlamlı türüdür [basic_iostream](../standard-library/basic-iostream-class.md), türündeki öğeler için özelleştirilmiş `wchar_t` varsayılan karakter nitelikler ile.

## <a name="wistream"></a>  wistream

Bir tür `basic_istream` üzerinde özel `wchar_t`.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için eş anlamlı türüdür [basic_istream](../standard-library/basic-istream-class.md), türündeki öğeler için özelleştirilmiş `wchar_t` varsayılan karakter nitelikler ile.

## <a name="see-also"></a>Ayrıca bkz.

[\<istream >](../standard-library/istream.md)<br/>
