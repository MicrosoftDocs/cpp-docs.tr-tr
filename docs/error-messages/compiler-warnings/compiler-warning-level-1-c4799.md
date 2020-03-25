---
title: Derleyici Uyarısı (düzey 1) C4799
ms.date: 11/04/2016
f1_keywords:
- C4799
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
ms.openlocfilehash: ec92da425718cd5ddc579d1d733a0bc4e56dc04a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175109"
---
# <a name="compiler-warning-level-1-c4799"></a>Derleyici Uyarısı (düzey 1) C4799

> '*Function*' işlevinin sonunda EMMS yok

İşlevde en az bir MMX yönergesi var, ancak bir `EMMS` yönergesi yok. Bir multimedya yönergesi kullanıldığında, MMX kodunun sonundaki çoklu ortam etiketi sözcüğünü temizlemek için bir `EMMS` yönergesi veya `_mm_empty` iç sürümü de kullanılmalıdır.

İvec. h kullanırken, kodun döndürmeden önce EMMS yönergesini doğru şekilde yürütümeyeceğini belirten C4799 alabilirsiniz. Bu üst bilgiler için bu yanlış bir uyarıdır. Bunu, IVEC. h içinde _SILENCE_IVEC_C4799 tanımlayarak kapatabilirsiniz. Bununla birlikte, derleyicinin bu türden doğru uyarıları vermekten de haberdar olacağını unutmayın.

İlgili bilgiler için bkz. [Intel 'ın MMX yönerge kümesi](../../assembler/inline/intel-s-mmx-instruction-set.md).
