---
title: "&lt;ostream&gt; tür tanımları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: bcf7df720a9b3a71ddbb32bd6eeb73f2f1332391
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; tür tanımları
|||  
|-|-|  
|[ostream](#ostream)|[wostream](#wostream)|  
  
##  <a name="ostream"></a>ostream  
 Bir tür üzerinde özelleştirilmiş basic_ostream oluşturur `char` ve `char_traits` üzerinde özel `char`.  
  
```
typedef basic_ostream<char, char_traits<char>> ostream;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_ostream](../standard-library/basic-ostream-class.md), türündeki öğeler için özelleştirilmiş `char` varsayılan karakter nitelikler ile.  
  
##  <a name="wostream"></a>wostream  
 Bir tür üzerinde özelleştirilmiş basic_ostream oluşturur `wchar_t` ve `char_traits` üzerinde özel `wchar_t`.  
  
```
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_ostream](../standard-library/basic-ostream-class.md), türündeki öğeler için özelleştirilmiş `wchar_t` varsayılan karakter nitelikler ile.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<ostream >](../standard-library/ostream.md)



