---
title: '&lt;ostream&gt; tür tanımları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: 8c451b16a581ab13f87c7bcca793efe3a0f07bf5
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; tür tanımları

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

Bir tür üzerinde özelleştirilmiş basic_ostream oluşturur `char` ve `char_traits` üzerinde özel `char`.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için eş anlamlı türüdür [basic_ostream](../standard-library/basic-ostream-class.md), türündeki öğeler için özelleştirilmiş `char` varsayılan karakter nitelikler ile.

## <a name="wostream"></a>  wostream

Bir tür üzerinde özelleştirilmiş basic_ostream oluşturur `wchar_t` ve `char_traits` üzerinde özel `wchar_t`.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için eş anlamlı türüdür [basic_ostream](../standard-library/basic-ostream-class.md), türündeki öğeler için özelleştirilmiş `wchar_t` varsayılan karakter nitelikler ile.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream >](../standard-library/ostream.md)<br/>
