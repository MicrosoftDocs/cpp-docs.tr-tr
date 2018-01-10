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
ms.workload: cplusplus
ms.openlocfilehash: 764bfd086612a10076e5c4800768b7b850ddbc7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Kaynak Dosyalar ve Kaynak Programlar](../c-language/source-files-and-source-programs.md)