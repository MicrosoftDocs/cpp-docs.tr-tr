---
title: Derleyici Uyarısı (düzey 1) C4799 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4799
dev_langs:
- C++
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f888d6a941ad487ce122e46c43582e1c96525c70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4799"></a>Derleyici Uyarısı (düzey 1) C4799  
  
> Hiçbir EMMS işlevi sonunda '*işlevi*'  
  
İşlev en az bir MMX yönerge olan, ancak sahip olmadığı bir `EMMS` yönergesi. Multimedya yönerge kullanıldığında, bir `EMMS` yönergesi veya `_mm_empty` iç ayrıca çoklu ortam etiketi word MMX kod sonunda temizlemek için kullanılmalıdır.  
  
Kod düzgün kullanmaz belirten ivec.h kullanarak yürüttüğünüzde dönmeden önce EMMS yönerge C4799 alabilirsiniz. Bu, bu üstbilgileri için yanlış bir uyarıdır. Bunlar içinde ivec.h _SILENCE_IVEC_C4799 tanımlayarak kapatabilirsiniz. Ancak, bu da derleyici bu tür doğru uyarıları vermiş saklar unutmayın.  
  
İlgili bilgi için bkz: [Intel'in MMX yönerge kümesi](../../assembler/inline/intel-s-mmx-instruction-set.md).