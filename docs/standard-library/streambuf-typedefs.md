---
title: '&lt;streambuf&gt; tür tanımları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: a9629bd9721d1e6089352cfb7fa8c2b40cbc00b7
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; tür tanımları

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a>  streambuf

Bir alt uzmanlaşması `basic_streambuf` kullanan `char` şablon parametreleri olarak.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için eş anlamlı türüdür [basic_streambuf](../standard-library/basic-streambuf-class.md), türündeki öğeler için özelleştirilmiş `char` varsayılan karakter nitelikler ile.

## <a name="wstreambuf"></a>  wstreambuf

Bir alt uzmanlaşması `basic_streambuf` kullanan `wchar_t` şablon parametreleri olarak.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için eş anlamlı türüdür [basic_streambuf](../standard-library/basic-streambuf-class.md), türündeki öğeler için özelleştirilmiş `wchar_t` varsayılan karakter nitelikler ile.

## <a name="see-also"></a>Ayrıca bkz.

[\<streambuf >](../standard-library/streambuf.md)<br/>
