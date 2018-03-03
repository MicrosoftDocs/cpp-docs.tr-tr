---
title: "Derleyici Hatası C2346 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2346
dev_langs:
- C++
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 769d5addc47ead8ffb338d5fbef313cd46735d31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2346"></a>Derleyici Hatası C2346
'function' derlenemiyor olarak yerel: nedeni  
  
 Derleyici MSIL işleve derleyemiyor.  
  
 Daha fazla bilgi için bkz: [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md) ve [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Kod için MSIL derlenemez işlevi kaldırın.  
  
2.  Ya da modülüyle derleme değil **/CLR**, ya da işlev yönetilmeyen pragma ile yönetilmeyen olarak işaretleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2346 oluşturur.  
  
```  
// C2346.cpp  
// processor: x86  
// compile with: /clr   
// C2346 expected  
struct S  
{  
   S()  
   {  
      { __asm { nop } }  
   }  
   virtual __clrcall ~S() { }  
};  
  
void main()  
{  
   S s;  
}  
```