---
title: "Derleyici Hatası C2289 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2289
dev_langs:
- C++
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 86527ef253b460a9ca5b68234d3f10cd87bc36fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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