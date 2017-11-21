---
title: "&lt;forward_list&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: 6696f42d2ba7cb6daabb8f2ff38093911838c1ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt; işlevleri
||  
|-|  
|[değiştirme](#swap)|  
  
##  <a name="swap"></a>değiştirme  
 İki iletme liste öğelerini değiş tokuş eder.  
  
```
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Türünde bir nesne `forward_list`.|  
|`right`|Türünde bir nesne `forward_list`.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablon işlevi yürütür `left.swap(right)`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< forward_list >](../standard-library/forward-list.md)



