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
ms.openlocfilehash: b3d83917289e5ad76a874587894a66e163fed90a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088234"
---
# <a name="compiler-warning-level-1-c4799"></a>Derleyici Uyarısı (düzey 1) C4799

> Hiçbir EMMS işlevi sonunda '*işlevi*'

İşlevi en az bir MMX yönerge, ancak sahip olmadığı bir `EMMS` yönergesi. Bir multimedya yönergesi kullanıldığında, bir `EMMS` yönerge veya `_mm_empty` iç ayrıca MMX kod sonunda multimedya etiketi word temizlemek için kullanılmalıdır.

Kodu düzgün kullanmaz belirten ivec.h, kullanarak yürütme, dönmeden önce EMMS yönergesi C4799 alabilirsiniz. Bu, bu üst bilgileri için yanlış bir uyarıdır. Bunlar içinde ivec.h _SILENCE_IVEC_C4799 tanımlayarak dışı. Ancak, bu da derleyici bu tür doğru uyarı vermesini tutacağını unutmayın.

İlgili bilgiler için bkz. [Intel'in MMX yönerge kümesi](../../assembler/inline/intel-s-mmx-instruction-set.md).