---
title: "Derleyici Hatası C2258 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2258
dev_langs: C++
helpviewer_keywords: C2258
ms.assetid: 105eaa87-befb-4ecb-9a3f-e09e14d2f5bf
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4db15da25ed6f7211c3260569a5c1add8c44c6a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2258"></a>Derleyici Hatası C2258
Geçersiz saf sözdizimi olması gerekir. '0 ='  
  
 Saf sanal işlevi yanlış sözdizimi ile bildirilir.  
  
 Aşağıdaki örnek C2258 oluşturur:  
  
```  
// C2258.cpp  
// compile with: /c  
class A {  
public:  
   void virtual func1() = 1; // C2258  
   void virtual func2() = 0;   // OK  
};  
```