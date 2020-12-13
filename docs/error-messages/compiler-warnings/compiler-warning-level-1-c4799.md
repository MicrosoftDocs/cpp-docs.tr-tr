---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4799'
title: Derleyici Uyarısı (düzey 1) C4799
ms.date: 11/04/2016
f1_keywords:
- C4799
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
ms.openlocfilehash: 9bfa84791a713d5ed5c0382402b958c255e30521
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334934"
---
# <a name="compiler-warning-level-1-c4799"></a>Derleyici Uyarısı (düzey 1) C4799

> '*Function*' işlevinin sonunda EMMS yok

İşlevde en az bir MMX yönergesi var, ancak bir `EMMS` yönergesi yok. Bir multimedya yönergesi kullanıldığında, `EMMS` `_mm_empty` MMX kodunun sonundaki çoklu ortam etiketi sözcüğünü temizlemek için bir yönerge veya iç değer de kullanılmalıdır.

İvec. h kullanırken, kodun döndürmeden önce EMMS yönergesini doğru şekilde yürütümeyeceğini belirten C4799 alabilirsiniz. Bu üst bilgiler için bu yanlış bir uyarıdır. Bunu, IVEC. h içinde _SILENCE_IVEC_C4799 tanımlayarak kapatabilirsiniz. Bununla birlikte, derleyicinin bu türden doğru uyarıları vermekten de haberdar olacağını unutmayın.

İlgili bilgiler için bkz. [Intel 'ın MMX yönerge kümesi](../../assembler/inline/intel-s-mmx-instruction-set.md).
