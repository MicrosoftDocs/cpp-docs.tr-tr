---
title: Derleyici Hatası C2232 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2232
dev_langs:
- C++
helpviewer_keywords:
- C2232
ms.assetid: 76f302b7-30a7-4a81-9a39-b4edde33b54c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 504f92a72b500548c2231958afa98ccdc177e12d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171317"
---
# <a name="compiler-error-c2232"></a>Derleyici Hatası C2232
'->': sol işleneni '' kullanmak sınıf anahtarı türe sahip, '.'  
  
 İşlenen solundaki `->` işleci bir işaretçi değil. Bir sınıf, yapı veya UNION nokta (.) işlecini kullanın.  
  
 Aşağıdaki örnek C2232 oluşturur:  
  
```  
// C2232.c  
struct X {  
    int member;  
} x, *px;  
int main() {  
    x->member = 0;   // C2232, x is not a pointer  
  
    px->member = 0;  
    x.member = 0;  
}  
```