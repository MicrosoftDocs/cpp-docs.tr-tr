---
title: "Derleyici Uyarısı (düzey 4) C4702 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4702
dev_langs: C++
helpviewer_keywords: C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ef7420f3699363d33d195e2455ab9fddf88de40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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