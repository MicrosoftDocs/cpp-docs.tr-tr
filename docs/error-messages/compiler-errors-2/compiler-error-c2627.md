---
title: Derleyici Hatası C2627 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2627
dev_langs:
- C++
helpviewer_keywords:
- C2627
ms.assetid: 7fc6c5ac-c7c9-4f0b-ad52-f52252526458
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67123349dd782beb9b547d3497d6c71d4390e434
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2627"></a>Derleyici Hatası C2627
'function': üye işlevi anonim birleşim içinde izin verilmiyor  
  
 Bir [anonim UNION](../../cpp/unions.md#anonymous_unions) üye işlevleri sahip olamaz.  
  
 Aşağıdaki örnek C2627 oluşturur:  
  
```  
// C2627.cpp  
int main() {  
   union { void f(){} };   // C2627  
   union X { void f(){} };  
}  
```