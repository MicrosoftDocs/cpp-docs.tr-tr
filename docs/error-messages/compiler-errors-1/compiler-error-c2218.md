---
title: Derleyici Hatası C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: db14c37992fc1e2dd409c653d622d3419fcae4f3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206654"
---
# <a name="compiler-error-c2218"></a>Derleyici Hatası C2218

' __vectorcall ', '/Arch: ıA32 ' ile kullanılamaz

`__vectorcall` çağırma kuralı yalnızca x86 ve x64 işlemcilerde Streaming SIMD Extensions 2 (SSE2) ve üstünü içeren yerel kodda desteklenir. Daha fazla bilgi için bkz. [__vectorcall](../../cpp/vectorcall.md).

Bu hatayı onarmak için derleyici seçeneklerini hedef SSE2, AVX veya AVX2 yönerge kümelerine değiştirin. Daha fazla bilgi için bkz. [/Arch (x86)](../../build/reference/arch-x86.md).
