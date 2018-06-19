---
title: Derleyici Uyarısı (Düzey 3) C4645 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4645
dev_langs:
- C++
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 718afb6b8336e36e0c0244cbdccd8af16ac4167f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292915"
---
# <a name="compiler-warning-level-3-c4645"></a>Derleyici Uyarısı (Düzey 3) C4645
__declspec(noreturn) ile bildirilen işlevi bir dönüş ifadesi içeriyor  
  
 A [dönmek](../../cpp/return-statement-in-program-termination-cpp.md) deyimi ile işaretlenen işlevde bulundu [noreturn](../../cpp/noreturn.md) `__declspec` değiştiricisi. `return` Deyimi yoksayıldı.  
  
 Aşağıdaki örnek C4645 oluşturur:  
  
```  
// C4645.cpp  
// compile with:  /W3  
void __declspec(noreturn) func() {  
   return;   // C4645, delete this line to resolve  
}  
  
int main() {  
}  
```