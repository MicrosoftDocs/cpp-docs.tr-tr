---
title: Derleyici Hatası C3498 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3498
dev_langs:
- C++
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6d895c0dc40d94d6a8fcd567173e2d596e68e333
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3498"></a>Derleyici Hatası C3498
'var': bir yönetilen sahip değişkeni veya WinRTtype yakalayamazsınız  
  
 Yönetilen tür veya bir Windows çalışma zamanı türü bir lambda sahip bir değişken yakalama yapılamaz.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Yönetilen geçirmek ya da Windows çalışma zamanı değişkenine lambda ifadesi parametre listesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yönetilen bir türe sahip bir değişken lambda ifadesi yakalama listesinde göründüğünden C3498 oluşturur:  
  
```  
// C3498a.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [&s](String ^ r)   
      { return String::Concat(s, r); } (", World!"); // C3498  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yönetilen değişkeni geçirerek C3498 çözümler `s` lambda ifadesi parametre listesi için:  
  
```  
// C3498b.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [](String ^ s, String ^ r)   
      { return String::Concat(s, r); } (s, ", World!");  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)