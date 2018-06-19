---
title: Derleyici Uyarısı (düzey 1) C4807 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4807
dev_langs:
- C++
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22710ee2b46a270e46aed7c043d4d988fcfaed62
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282369"
---
# <a name="compiler-warning-level-1-c4807"></a>Derleyici Uyarısı (düzey 1) C4807
'işlemi': güvensiz karışımını türü 'type' ve ' type' türünde imzalı saklayıcısında  
  
 Bu uyarı için bir bit imzalı bit alan karşılaştırma zaman oluşturulan bir `bool` değişkeni. Bir bit, imzalı bit alan değerleri -1 veya 0 yalnızca içerebileceğinden kendisine Karşılaştırılacak tehlikeli `bool`. Uyarı karıştırma hakkında oluşturulan `bool` ve aynı olduğundan bir bit, imzasız bit alanları `bool` ve yalnızca 0 veya 1 tutabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4807 oluşturur:  
  
```  
// C4807.cpp  
// compile with: /W1  
typedef struct bitfield {  
   signed mybit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bool b = true;  
  
   // try..  
   // int b = true;  
  
   bf.mybit = -1;  
   if (b == bf.mybit) {   // C4807  
      b = false;  
   }  
}  
```