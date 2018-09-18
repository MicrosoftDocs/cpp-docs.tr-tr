---
title: Derleyici Hatası C2218 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2218
dev_langs:
- C++
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52c449381c6e8a7391706ed6097bc38576bc69fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041291"
---
# <a name="compiler-error-c2218"></a>Derleyici Hatası C2218

'__vectorcall' kullanılamaz ' / arch: IA32'

`__vectorcall` Çağırma kuralı yalnızca desteklenen yerel kodda, Streaming SIMD Extensions 2 (SSE2) içeren x86 ve x64 işlemciler ve üzeri. Daha fazla bilgi için [__vectorcall](../../cpp/vectorcall.md).

Bu hatayı düzeltmek için hedef SSE2, AVX veya AVX2 yönerge kümesi için derleyici seçeneklerini değiştirin. Daha fazla bilgi için [/arch (x86)](../../build/reference/arch-x86.md).