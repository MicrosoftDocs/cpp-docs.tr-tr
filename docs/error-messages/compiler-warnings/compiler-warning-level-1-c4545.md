---
title: "Derleyici Uyarısı (düzey 1) C4545 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4545
dev_langs:
- C++
helpviewer_keywords:
- C4545
ms.assetid: 43f8f34f-ed46-4661-95c0-c588c577ff73
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe396267981bd534c373a101bd3e28827a343c37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4545"></a>Derleyici Uyarısı (düzey 1) C4545
virgülden önceki ifade bir bağımsız değişken listesi olmayan bir işlev olarak değerleniyor  
  
 Derleyici hatalı oluşturulmuş virgülle ifade algıladı.  
  
 Varsayılan olarak bu uyarı kapalıdır. Daha fazla bilgi için bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Aşağıdaki örnek C4545 oluşturur:  
  
```  
// C4545.cpp  
// compile with: /W1  
#pragma warning (default : 4545)  
  
void f() { }  
  
int main()  
{  
   *(&f), 10;   // C4545  
   // try the following line instead  
   // (*(&f))(), 10;  
}  
```