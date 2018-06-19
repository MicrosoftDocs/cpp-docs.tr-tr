---
title: Derleyici Hatası C3498 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3498
dev_langs:
- C++
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 913caa8fc73e5fe325a9d17a48b6c2b9ba641546
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254461"
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