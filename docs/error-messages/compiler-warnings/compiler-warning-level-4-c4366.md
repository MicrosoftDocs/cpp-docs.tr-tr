---
title: Derleyici Uyarısı (düzey 4) C4366 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4366
dev_langs:
- C++
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12410a567cb55d6dea74b8e5e595009e56b1071f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293708"
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