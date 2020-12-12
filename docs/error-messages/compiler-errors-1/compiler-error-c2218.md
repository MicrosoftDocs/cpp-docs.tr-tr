---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2218'
title: Derleyici Hatası C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: d2761bb822c5a1055974e4a0bcd6011e7f451821
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245531"
---
# <a name="compiler-error-c2218"></a>Derleyici Hatası C2218

> ' __vectorcall ', '/Arch: ıA32 ' ile kullanılamaz

**`__vectorcall`** Çağırma kuralı yalnızca, Streaming SIMD Extensions 2 (SSE2) ve üstünü içeren x86 ve x64 işlemcilerde yerel kodda desteklenir. Daha fazla bilgi için bkz. [`__vectorcall`](../../cpp/vectorcall.md).

Bu hatayı onarmak için derleyici seçeneklerini hedef SSE2, AVX veya AVX2 yönerge kümelerine değiştirin. Daha fazla bilgi için bkz. [ `/arch` (x86)](../../build/reference/arch-x86.md).
