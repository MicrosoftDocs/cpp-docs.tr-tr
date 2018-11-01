---
title: Derleyici Hatası C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: 5a9d897686fc915c9892fa2bcd51fa3ca3c8b05e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468631"
---
# <a name="compiler-error-c2218"></a>Derleyici Hatası C2218

'__vectorcall' kullanılamaz ' / arch: IA32'

`__vectorcall` Çağırma kuralı yalnızca desteklenen yerel kodda, Streaming SIMD Extensions 2 (SSE2) içeren x86 ve x64 işlemciler ve üzeri. Daha fazla bilgi için [__vectorcall](../../cpp/vectorcall.md).

Bu hatayı düzeltmek için hedef SSE2, AVX veya AVX2 yönerge kümesi için derleyici seçeneklerini değiştirin. Daha fazla bilgi için [/arch (x86)](../../build/reference/arch-x86.md).