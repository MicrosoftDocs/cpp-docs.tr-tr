---
title: "Derleyici Uyarısı (düzey 1) C4807 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4807
dev_langs:
- C++
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af604a1a045b9dbef7b3c27f9c7aabd0040aa318
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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