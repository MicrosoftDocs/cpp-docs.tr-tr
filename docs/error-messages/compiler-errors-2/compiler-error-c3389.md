---
title: Derleyici Hatası C3389 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3389
dev_langs:
- C++
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f0f60a1096c070d28be3b7af161bbb924fb20dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3389"></a>Derleyici Hatası C3389
/ CLR ile __declspec(Keyword) kullanılamaz: Saf veya/CLR: safe  
  
 **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
 A [__declspec](../../cpp/declspec.md) kullanılan değiştiricisi gelir bir başına işlem durumu.  [/ CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md) gelir bir başına [appdomain](../../cpp/appdomain.md) durumu.  Bu nedenle, sahip bir değişken bildirme `keyword` **__declspec** değiştiricisini ve ile derleme **/CLR: pure** verilmez.  
  
 Aşağıdaki örnek C3389 oluşturur:  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```