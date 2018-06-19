---
title: Derleyici Hatası C3899 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3899
dev_langs:
- C++
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f40f1065514437463be06a89f01e067c4324cd2e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276002"
---
# <a name="compiler-error-c3899"></a>Derleyici Hatası C3899
'var': l-değeri kullanım initonly veri üyesi doğrudan sınıfı 'sınıfı' paralel bir bölgede içinde izin verilmeyen  
  
 Bir [initonly (C + +/ CLI)](../../dotnet/initonly-cpp-cli.md) veri üyesi olan bir oluşturucu kısmı içinde başlatılamıyor bir [paralel](../../parallel/openmp/reference/parallel.md) bölge.  Derleyici bu kodu bir iç konumlandırmasını yaptığından etkili bir şekilde artık Oluşturucusu parçası olan şekilde budur.  
  
 Çözmek için initonly veri üyesi oluşturucuda ancak paralel bölgesi dışında başlatır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3899 oluşturur.  
  
```  
// C3899.cpp  
// compile with: /clr /openmp  
#include <omp.h>   
  
public ref struct R {  
   initonly int x;  
   R() {  
      x = omp_get_thread_num() + 1000;   // OK  
      #pragma omp parallel num_threads(5)  
      {  
         // cannot assign to 'x' here  
         x = omp_get_thread_num() + 1000;   // C3899  
         System::Console::WriteLine("thread {0}", omp_get_thread_num());  
      }  
      x = omp_get_thread_num() + 1000;   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R;  
   System::Console::WriteLine(r->x);  
}  
```