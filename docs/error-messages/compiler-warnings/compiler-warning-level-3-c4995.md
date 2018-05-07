---
title: Derleyici Uyarısı (Düzey 3) C4995 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4995
dev_langs:
- C++
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c6bf1bbab4ee9a5a08a1376c91c6a7bba160625
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4995"></a>Derleyici Uyarısı (Düzey 3) C4995
'function': ad, kullanım dışı #pragma işaretlendi  
  
 Pragma ile işaretlenmiş bir işlev derleyici karşılaştı [kullanım dışı](../../preprocessor/deprecated-c-cpp.md). İşlev, gelecekteki bir sürümde desteklenmiyor olabilir. Bu uyarı ile kapatabilirsiniz [uyarı](../../preprocessor/warning.md) pragma (Aşağıdaki örnek).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4995 oluşturur:  
  
```  
// C4995.cpp  
// compile with: /W3  
#include <stdio.h>  
  
// #pragma warning(disable : 4995)  
void func1(void)  
{  
    printf("\nIn func1");  
}  
  
int main()   
{  
    func1();  
    #pragma deprecated(func1)  
    func1();   // C4995  
}  
```