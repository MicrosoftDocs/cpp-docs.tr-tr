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
ms.openlocfilehash: 1efda7258616862efc464b493b51ada2c6bd7674
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172217"
---
# <a name="compiler-error-c2218"></a>Derleyici Hatası C2218
'__vectorcall' ile kullanılamaz ' / arch: IA32'  
  
 `__vectorcall` Çağırma yalnızca desteklenen yerel kodda Streaming SIMD Extensions 2 (SSE2) dahil x86 hem x64 işlemciler ve üstü. Daha fazla bilgi için bkz: [__vectorcall](../../cpp/vectorcall.md).  
  
 Bu hatayı düzeltmek için hedef SSE2, AVX ya da AVX2 yönerge kümelerini derleyici seçeneklerini değiştirin. Daha fazla bilgi için bkz: [/(x86) arch](../../build/reference/arch-x86.md).