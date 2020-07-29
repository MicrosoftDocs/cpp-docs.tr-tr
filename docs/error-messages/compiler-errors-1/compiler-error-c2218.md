---
title: Derleyici Hatası C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: 97f3290ef8bcb6a91442effdbf84261c03545ce2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87209532"
---
# <a name="compiler-error-c2218"></a>Derleyici Hatası C2218

> ' __vectorcall ', '/Arch: ıA32 ' ile kullanılamaz

**`__vectorcall`** Çağırma kuralı yalnızca, Streaming SIMD Extensions 2 (SSE2) ve üstünü içeren x86 ve x64 işlemcilerde yerel kodda desteklenir. Daha fazla bilgi için bkz. [`__vectorcall`](../../cpp/vectorcall.md).

Bu hatayı onarmak için derleyici seçeneklerini hedef SSE2, AVX veya AVX2 yönerge kümelerine değiştirin. Daha fazla bilgi için bkz. [ `/arch` (x86)](../../build/reference/arch-x86.md).
