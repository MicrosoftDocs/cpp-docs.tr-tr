---
title: Derleyici Uyarısı (düzey 1) C4835 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4835
dev_langs:
- C++
helpviewer_keywords:
- C4835
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f078b128bfb3cd50707208e78b49ee1b8b3c5c35
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4835"></a>Derleyici Uyarısı (düzey 1) C4835
'değişkeni': yönetilen kod ilk ana bilgisayarı bütünleştirilmiş kodunda yürütülene dek dışarı aktarılan veriler için Başlatıcı çalıştırılmaz  
  
 Yönetilen bileşenleri arasında verilere erişirken değil yerel C++ içe aktarma işlemi kullanın ve mekanizmaları verme önerilir. Bunun yerine, bir yönetilen türü içinde veri üyeleri bildirme ve meta verileri ile başvuru `#using` istemci. Daha fazla bilgi için bkz: [#using yönergesi](../../preprocessor/hash-using-directive-cpp.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4835 oluşturur.  
  
```  
// C4835.cpp  
// compile with: /W1 /clr /LD  
int f() { return 1; }  
int n = 9;  
  
__declspec(dllexport) int m = f();   // C4835  
__declspec(dllexport) int *p = &n;   // C4835  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, önceki örnekte, değişkenlerin değerini beklendiği gibi olduğunu gösteren yerleşik bileşeni kullanır.  
  
```  
// C4835_b.cpp  
// compile with: /clr C4835.lib  
#include <stdio.h>  
__declspec(dllimport) int m;  
__declspec(dllimport) int *p;  
  
int main() {  
   printf("%d\n", m);  
   printf("%d\n", p);  
}  
```  
  
```Output  
0  
268456008  
```