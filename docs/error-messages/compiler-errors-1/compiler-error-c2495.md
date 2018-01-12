---
title: "Derleyici Hatası C2495 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2495
dev_langs: C++
helpviewer_keywords: C2495
ms.assetid: bb7066fe-3549-4901-97e4-157f3c04dd57
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 377654c83375b83afdf168f3abf063ddebcd5558
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2495"></a>Derleyici Hatası C2495
'tanımlayıcısı': 'nothrow', yalnızca işlev bildirimleri ya da tanımları uygulanabilir  
  
 [Nothrow](../../cpp/nothrow-cpp.md) işlev bildirimleri ya da yalnızca tanımları için genişletilmiş öznitelik uygulanabilir.  
  
 Aşağıdaki örnek C2495 oluşturur:  
  
```  
// C2495.cpp  
// compile with: /c  
__declspec(nothrow) class X {   // C2495  
   int m_data;  
} x;  
  
__declspec(nothrow) void test();   // OK  
```