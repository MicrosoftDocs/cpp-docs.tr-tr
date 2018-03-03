---
title: "Derleyici Hatası C3389 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3389
dev_langs:
- C++
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd88753553d2bad1cb9253cfe709e7627c4b01ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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