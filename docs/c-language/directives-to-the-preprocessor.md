---
title: "Ön İşlemci yönergeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 39f1e29a2bc8b72d5b2467c248a4d12b63baa26b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="directives-to-the-preprocessor"></a>Ön işlemci Yönergeleri
"Yönergesi" programı derleme önce metni belirli bir eylemi gerçekleştirmek için önişlemci C bildirir. [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) tam olarak açıklanan *önişlemci başvurusu*. Bu örnek önişlemci yönergesi kullanır `#define`:  
  
```  
#define MAX 100  
```  
  
 Derleyicinin her oluşumu değiştirmek için bu bildirimi söyler `MAX` tarafından `100` derleme önce. C Derleyici önişlemci yönergeleri şunlardır:  
  
|#define|#endif|#ifdef|#line|  
|--------------|-------------|-------------|------------|  
|`#elif`|`#error`|**#ifndef**|**#pragma**|  
|`#else`|`#if`|`#include`|`#undef`|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyalar ve kaynak programlar](../c-language/source-files-and-source-programs.md)