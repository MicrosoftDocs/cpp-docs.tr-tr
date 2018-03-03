---
title: "Derleyici Hatası C2218 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2218
dev_langs:
- C++
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cce36d9e8d4e8f2ac82ddec9a967ac7e045b4a03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2218"></a>Derleyici Hatası C2218
'__vectorcall' ile kullanılamaz ' / arch: IA32'  
  
 `__vectorcall` Çağırma yalnızca desteklenen yerel kodda Streaming SIMD Extensions 2 (SSE2) dahil x86 hem x64 işlemciler ve üstü. Daha fazla bilgi için bkz: [__vectorcall](../../cpp/vectorcall.md).  
  
 Bu hatayı düzeltmek için hedef SSE2, AVX ya da AVX2 yönerge kümelerini derleyici seçeneklerini değiştirin. Daha fazla bilgi için bkz: [/(x86) arch](../../build/reference/arch-x86.md).