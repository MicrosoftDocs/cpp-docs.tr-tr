---
title: "Derleyici Uyarısı (düzey 4) C4366 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4366
dev_langs: C++
helpviewer_keywords: C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d610bfcf2e432870fc081298d3dfc3a60c73bd4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4366"></a>Derleyici Uyarısı (düzey 4) C4366
Birli 'işleci' işlecinin sonucu hizalanmamış olabilir  
  
 Yapı üyesi hiç paket nedeniyle hizalanmamış olabilir, derleyici ne zaman üyenin adresi hizalı bir işaretçi atanır sizi uyarır. Varsayılan olarak, tüm işaretçiler hizalanır.  
  
 C4366 çözmek için yapıyı hizalamasını değiştirme ya da işaretçi bildirme [__unaligned](../../cpp/unaligned.md) anahtar sözcüğü.  
  
 Daha fazla bilgi için bkz: __unaligned ve [paketi](../../preprocessor/pack.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4366 oluşturur.  
  
```  
// C4366.cpp  
// compile with: /W4 /c  
// processor: IPF x64  
#pragma pack(1)  
struct X {  
   short s1;  
   int s2;  
};  
  
int main() {  
   X x;  
   short * ps1 = &x.s1;   // OK  
   int * ps2 = &x.s2;   // C4366  
}  
```