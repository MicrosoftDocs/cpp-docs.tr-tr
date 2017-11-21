---
title: "Derleyici Hatası C2218 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2218
dev_langs: C++
helpviewer_keywords: C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3ca2e431fdfeff3c9dc957bee46f84cfd2c04162
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2218"></a>Derleyici Hatası C2218
'__vectorcall' ile kullanılamaz ' / arch: IA32'  
  
 `__vectorcall` Çağırma yalnızca desteklenen yerel kodda Streaming SIMD Extensions 2 (SSE2) dahil x86 hem x64 işlemciler ve üstü. Daha fazla bilgi için bkz: [__vectorcall](../../cpp/vectorcall.md).  
  
 Bu hatayı düzeltmek için hedef SSE2, AVX ya da AVX2 yönerge kümelerini derleyici seçeneklerini değiştirin. Daha fazla bilgi için bkz: [/(x86) arch](../../build/reference/arch-x86.md).