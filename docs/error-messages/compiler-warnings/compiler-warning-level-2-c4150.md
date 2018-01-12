---
title: "Derleyici Uyarısı (Düzey 2) C4150 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4150
dev_langs: C++
helpviewer_keywords: C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09267a909ea6e4b0bedd43e6f31a31e778ffb904
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4150"></a>Derleyici Uyarısı (Düzey 2) C4150
silme işaretçinin tamamlanmamış türü 'type'; adlı hiçbir yok Edicisi  
  
 **Silmek** işleci derleyici bir yıkıcı bulmanız bildirilen ancak tanımlı değilse, bir türünü silmek için çağrılır.  
  
 Aşağıdaki örnek C4150 oluşturur:  
  
```  
// C4150.cpp  
// compile with: /W2  
class  IncClass;  
  
void NoDestruct( IncClass* pIncClass )  
{  
   delete pIncClass;  
} // C4150, define class to resolve  
  
int main()  
{  
}  
```