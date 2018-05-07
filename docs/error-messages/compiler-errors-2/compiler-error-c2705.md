---
title: Derleyici Hatası C2705 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2705
dev_langs:
- C++
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dce6bdb0a5c20fbe54b04eaf83ee8f90427017c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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