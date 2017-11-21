---
title: "Derleyici Hatası C2705 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2705
dev_langs: C++
helpviewer_keywords: C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 734287b37835d196ebfc131bc5f9392d0a712f3e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2705"></a>Derleyici Hatası C2705
'etiket': 'özel durum işleyici bloğunun' kapsam içine geçersiz atlama  
  
 Yürütme atlar içinde bir etiket için bir `try` / `catch`, `__try` / `__except`, `__try` / `__finally` bloğu. Daha fazla bilgi için bkz: [özel durum işleme](../../cpp/exception-handling-in-visual-cpp.md).  
  
 Aşağıdaki örnek C2705 oluşturur:  
  
```  
// C2705.cpp  
int main() {  
goto trouble;  
   __try {  
      trouble: ;   // C2705  
   }  
   __finally {}  
  
   // try the following line instead  
   // trouble: ;  
}  
```