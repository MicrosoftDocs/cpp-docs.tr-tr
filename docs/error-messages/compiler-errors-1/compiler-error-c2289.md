---
title: Derleyici Hatası C2289 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2289
dev_langs:
- C++
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d351bffc33fc754ffcb66d2428a77fb040089a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2289"></a>Derleyici Hatası C2289
birden çok kez kullanılan aynı tür niteleyicisi  
  
 Tür niteleyicisi türü bildirimi veya tanımı kullanır (`const`, `volatile`, `signed`, veya `unsigned`) birden fazla kez ANSI Uyumluluğu altında bir hata neden (**/Za**).  
  
 Aşağıdaki örnek C2286 oluşturur:  
  
```  
// C2289.cpp  
// compile with: /Za /c  
volatile volatile int i;   // C2289  
volatile int j;   // OK  
```