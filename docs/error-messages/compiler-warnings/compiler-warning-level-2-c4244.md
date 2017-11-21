---
title: "Derleyici Uyarısı (Düzey 2) C4244 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4244
dev_langs: C++
helpviewer_keywords: C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7f2059d6b17d803740f70e0d640e212d15858705
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4244"></a>Derleyici Uyarısı (Düzey 2) C4244
'bağımsız değişkeni': 'type1' öğesinden 'type2', olası veri kaybını dönüştürme  
  
 Bir kayan nokta türünü bir tamsayı türüne dönüştürüldü.  Olası veri kaybını oluşmuş olabilir.  
  
 C4244 alırsanız, uyumlu türleri kullanılacak programınızı değiştirmek veya olası değerleri aralığı her zaman, kullanmakta olduğunuz türleri ile uyumlu olmasını sağlamak için kodunuzun bazı mantığı ekleyin.  
  
 C4244 3 ve 4 düzeyinde de tetikleyebilir; bkz: [Derleyici Uyarısı (Düzey 3 ve 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4244 oluşturur:  
  
```  
// C4244_level2.cpp  
// compile with: /W2  
  
int f(int x){ return 0; }  
int main() {  
   double x = 10.1;  
   int i = 10;  
   return (f(x));   // C4244  
   // try the following line instead  
   // return (f(i));  
}  
```