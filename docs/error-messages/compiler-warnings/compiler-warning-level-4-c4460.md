---
title: Derleyici Uyarısı (düzey 4) C4460 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4460
dev_langs:
- C++
helpviewer_keywords:
- C4460
ms.assetid: c97ac1c9-598d-479e-bfff-c993690c4f3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3eacdb57dbe3fd657ffb6d1b7612424fe5b4f77
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293760"
---
# <a name="compiler-warning-level-4-c4460"></a>Derleyici Uyarısı (düzey 4) C4460
WinRT veya CLR operator 'işleci', başvuruya göre parametresi geçildi. WinRT veya CLR operator 'işleci' 'işleci' C++ işleci öğesinden farklı semantiklerine sahip, değere göre geçirilecek istiyordunuz?  
  
 Kullanıcı tanımlı Windows çalışma zamanı veya CLR işleci başvuruya göre bir değer geçirildi. Değer işlevinde değiştirdiyseniz, işlev çağrısı işlevinin dönüş değeri atanacak sonra döndürülen değer unutmayın. Standart C++'da, değiştirilen değer işlev çağrısı sonra yansıtılır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4460 oluşturur ve nasıl düzeltileceği gösterir.  
  
```  
// C4460.cpp  
// compile with: /W4 /clr   
#include <stdio.h>  
  
public value struct V {  
   static V operator ++(V& me) {   // C4460  
   // try the following line instead  
   // static V operator ++(V me) {  
  
      printf_s(__FUNCSIG__ " called\n");  
      V tmp = me;  
      me.m_i++;  
      return tmp;  
   }  
   int m_i;  
};  
  
int main() {  
   V v;  
   v.m_i = 0;  
  
   printf_s("%d\n", v.m_i);   // Should print 0  
   v++;   // Translates to "v = V::operator ++(v)"  
   printf_s("%d\n", v.m_i);   // will print 0, hence the warning  
}  
```