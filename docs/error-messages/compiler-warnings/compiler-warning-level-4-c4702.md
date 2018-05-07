---
title: Derleyici Uyarısı (düzey 4) C4702 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4702
dev_langs:
- C++
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29c2d6b0328fd8dd4cd6f9a226253036b62d03ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4702"></a>Derleyici Uyarısı (düzey 4) C4702
koda erişilemiyor  
  
 Bu uyarı için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucudur: koda erişilemiyor. Derleyici (arka uç) ulaşılamaz kod algıladığında C4702, oluşturur düzey 4 uyarı.  
  
 Visual C++, Visual Studio .NET 2003 ve Visual Studio sürümlerinde geçerli olan kodu için ulaşılamaz kod kaldırın veya tüm kaynak kodu yürütme bazı akış tarafından erişilebilir olduğunu güvence altına alır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4702 oluşturur.  
  
```  
// C4702.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main() {  
   return 1;  
   printf_s("I won't print.\n");   // C4702 unreachable  
}  
```  
  
## <a name="example"></a>Örnek  
 İle derleme yapılırken **/GX**, **/EHc**, **/EHsc**, veya **/EHac** ve extern C işlevleri kullanarak, kodu erişilemiyor olabilir çünkü extern C işlev oluşturma için kabul edilir, böylece catch bloğu erişilebilir değil.  İle bir işlev atabilirsiniz çünkü bu uyarıyı geçersiz olduğunu düşünüyorsanız, derleme **/EHa** veya **/EHs**bağlı olarak özel durum belirtildi.  
  
 Daha fazla bilgi için bkz: [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4702 oluşturur.  
  
```  
// C4702b.cpp  
// compile with: /W4 /EHsc  
#include <iostream>  
  
using namespace std;  
extern "C" __declspec(dllexport) void Function2(){}  
  
int main() {  
   try {  
      Function2();  
   }  
   catch (...) {  
      cout << "Exp: Function2!" << endl;   // C4702  
   }  
}  
```