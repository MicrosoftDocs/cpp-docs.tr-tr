---
title: Ön İşlemci yönergeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 711e28a569cefbb500a98ab33cd22c527a5fd7c5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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