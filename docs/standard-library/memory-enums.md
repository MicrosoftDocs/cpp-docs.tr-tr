---
title: "&lt;bellek&gt; numaralandırmaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: 52ccd226214da7ddbdca9c480bb2f8940203155e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltmemorygt-enums"></a>&lt;bellek&gt; numaralandırmaları
||  
|-|  
|[pointer_safety](#pointer_safety)|  
  
##  <a name="pointer_safety"></a>pointer_safety numaralandırması  
 Olası değerler tarafından döndürülen numaralandırma `get_pointer_safety`.  
  
sınıf pointer_safety {gevşek, tercih edilen, katı};  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsamlı `enum` tarafından döndürülen değerleri tanımlar `get_pointer_safety()`:  
  
 `relaxed`--güvenli bir biçimde türetilmiş işaretçileri (açıkça bildirilen veya ayrılmış nesnelerine işaretçiler) kabul edilir aynı Bu güvenle türetilmiş.  
  
 `preferred`--eskisi, ancak güvenli bir biçimde türetilmiş işaretçileri değil başvuru yapıldı.  
  
 `strict`--güvenli bir biçimde türetilmiş işaretçileri kabul Bu güvenle türetilmiş farklı bir biçimde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<bellek >](../standard-library/memory.md)



