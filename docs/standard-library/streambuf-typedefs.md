---
title: "&lt;streambuf&gt; tür tanımları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: 932b5ce7a664f75eb92f19fdbf32363b9300fb09
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; tür tanımları
|||  
|-|-|  
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|  
  
##  <a name="streambuf"></a>streambuf  
 Bir alt uzmanlaşması `basic_streambuf` kullanan `char` şablon parametreleri olarak.  
  
```
typedef basic_streambuf<char, char_traits<char>> streambuf;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_streambuf](../standard-library/basic-streambuf-class.md), türündeki öğeler için özelleştirilmiş `char` varsayılan karakter nitelikler ile.  
  
##  <a name="wstreambuf"></a>wstreambuf  
 Bir alt uzmanlaşması `basic_streambuf` kullanan `wchar_t` şablon parametreleri olarak.  
  
```
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_streambuf](../standard-library/basic-streambuf-class.md), türündeki öğeler için özelleştirilmiş `wchar_t` varsayılan karakter nitelikler ile.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<streambuf >](../standard-library/streambuf.md)



