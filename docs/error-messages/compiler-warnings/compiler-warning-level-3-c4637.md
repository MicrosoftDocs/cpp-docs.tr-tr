---
title: Derleyici Uyarısı (Düzey 3) C4637 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4637
dev_langs:
- C++
helpviewer_keywords:
- C4637
ms.assetid: 5fd347c1-2de9-408f-9136-1bf1ff273622
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 192cec5940cb813ab5057cf179b7f67feb1d0f78
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4637"></a>Derleyici Uyarısı (Düzey 3) C4637
XML Belge açıklama hedef: \<dahil > etiketi atılır.  Nedeni  
  
 Söz dizimi bir [ \<dahil >](../../ide/include-visual-cpp.md) etiketi doğru değildi.  
  
 Aşağıdaki örnek C4637 oluşturur:  
  
```  
// C4637.cpp  
// compile with: /clr /doc /LD /W3  
using namespace System;  
  
/// Text for class MyClass.  
public ref class MyClass {   
public:  
   /// <include file="c:\davedata\jtest\xml_include.doc"/>  
   // Try the following line instead:  
   // /// <include file='xml_include.doc' path='MyDocs/MyMembers/*' />  
   void MyMethod() {  
   }  
};   // C4637  
```