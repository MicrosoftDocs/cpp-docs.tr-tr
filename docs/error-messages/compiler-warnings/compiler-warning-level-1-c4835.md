---
title: "Derleyici Uyarısı (düzey 1) C4835 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4835
dev_langs:
- C++
helpviewer_keywords:
- C4835
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92e2d17ada58773a34d8c2d14424dd88e74a06d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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