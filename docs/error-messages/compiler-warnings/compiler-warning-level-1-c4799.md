---
title: Derleyici Uyarısı (düzey 1) C4799
ms.date: 11/04/2016
f1_keywords:
- C4799
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
ms.openlocfilehash: 475451b47d461e7ea1428eb715a876fb023694d1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552262"
---
# <a name="compiler-warning-level-1-c4799"></a>Derleyici Uyarısı (düzey 1) C4799

> Hiçbir EMMS işlevi sonunda '*işlevi*'

İşlevi en az bir MMX yönerge, ancak sahip olmadığı bir `EMMS` yönergesi. Bir multimedya yönergesi kullanıldığında, bir `EMMS` yönerge veya `_mm_empty` iç ayrıca MMX kod sonunda multimedya etiketi word temizlemek için kullanılmalıdır.

Kodu düzgün kullanmaz belirten ivec.h, kullanarak yürütme, dönmeden önce EMMS yönergesi C4799 alabilirsiniz. Bu, bu üst bilgileri için yanlış bir uyarıdır. Bunlar içinde ivec.h _SILENCE_IVEC_C4799 tanımlayarak dışı. Ancak, bu da derleyici bu tür doğru uyarı vermesini tutacağını unutmayın.

İlgili bilgiler için bkz. [Intel'in MMX yönerge kümesi](../../assembler/inline/intel-s-mmx-instruction-set.md).