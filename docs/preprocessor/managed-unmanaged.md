---
title: "yönetilen, yönetilmeyen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.unmanaged
- managed_CPP
- unmanaged_CPP
- vc-pragma.managed
dev_langs: C++
helpviewer_keywords:
- managed pragma
- pragmas, unmanaged
- pragmas, managed
- unmanaged pragma
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2d8e2b50f7d505a4e262559b6cb69b0bab81ffcd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="managed-unmanaged"></a>managed, unmanaged
Derleme yönetilen veya yönetilmeyen olarak işlevler için işlev düzeyi denetimi etkinleştirin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      #pragma managed  
#pragma unmanaged  
#pragma managed([push,] on | off)  
#pragma managed(pop)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği işlevleri yönetilen veya yönetilmeyen olarak derlemek için modülü düzey denetim sağlar.  
  
 Yönetilmeyen bir işleve yerel platformu derlenir ve söz konusu bölümü programın yürütülmesi için yerel platform ortak dil çalışma zamanı tarafından geçirilir.  
  
 İşlevler, varsayılan olarak yönetilen olarak derlenen zaman **/CLR** kullanılır.  
  
 Bu pragmaları uygularken:  
  
-   Bir işlev önceki pragma eklemek ancak işlev gövdesi içinde değil.  
  
-   Pragma sonra Ekle `#include` deyimleri. Önce bu pragmaları kullanmayın `#include` deyimleri.  
  
 Derleyici yoksayar `managed` ve `unmanaged` pragmaları varsa **/CLR** derlemede kullanılmaz.  
  
 Bir şablon işlevi örneği oluşturulduğunda tanımı şablonu için zaman pragma durumunu, yönetilen yönetilmeyen mi olduğunu belirler.  
  
 Daha fazla bilgi için bkz: [karışık derlemeleri başlatma](../dotnet/initialization-of-mixed-assemblies.md).  
  
## <a name="example"></a>Örnek  
  
```cpp  
// pragma_directives_managed_unmanaged.cpp  
// compile with: /clr  
#include <stdio.h>  
  
// func1 is managed  
void func1() {  
   System::Console::WriteLine("In managed function.");  
}  
  
// #pragma unmanaged  
// push managed state on to stack and set unmanaged state  
#pragma managed(push, off)  
  
// func2 is unmanaged  
void func2() {  
   printf("In unmanaged function.\n");  
}  
  
// #pragma managed  
#pragma managed(pop)  
  
// main is managed  
int main() {  
   func1();  
   func2();  
}  
```  
  
```Output  
In managed function.  
In unmanaged function.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)