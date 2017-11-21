---
title: "Derleyici Uyarısı (düzey 1) C4353 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4353
dev_langs: C++
helpviewer_keywords: C4353
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b64e2a43f6d85499c1884a9cc14e6f615f7bf8b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4353"></a>Derleyici Uyarısı (düzey 1) C4353
kullanılan standart olmayan uzantısı: sabit 0 olarak işlev ifadesi. Bunun yerine '__noop' işlevini iç kullanın  
  
 Bir işlev ifadesi olarak sabit sıfır (0) kullanamazsınız. Daha fazla bilgi için bkz: [__noop](../../intrinsics/noop.md).  
  
 Aşağıdaki örnek C4353 oluşturur:  
  
```  
// C4353.cpp  
// compile with: /W1  
void MyPrintf(void){};  
#define X 0  
#if X  
   #define DBPRINT MyPrint  
#else  
   #define DBPRINT 0   // C4353 expected  
#endif  
int main(){  
DBPRINT();  
}  
```