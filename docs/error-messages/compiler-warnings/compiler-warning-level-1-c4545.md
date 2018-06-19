---
title: Derleyici Uyarısı (düzey 1) C4545 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4545
dev_langs:
- C++
helpviewer_keywords:
- C4545
ms.assetid: 43f8f34f-ed46-4661-95c0-c588c577ff73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5f34dbdb420fffefdd07f79ae651002cfe67598
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278281"
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