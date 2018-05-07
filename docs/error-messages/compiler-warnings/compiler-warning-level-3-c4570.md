---
title: Derleyici Uyarısı (Düzey 3) C4570 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4570
dev_langs:
- C++
helpviewer_keywords:
- C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a79b6afae4bc14e5fcd2dc4979ebd29c60c15b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4570"></a>Derleyici Uyarısı (Düzey 3) C4570
'type': soyut ancak soyut işlevleri taşıdığından açıkça bildirilmedi  
  
 İçeren bir türü [soyut](../../windows/abstract-cpp-component-extensions.md) işlevleri kendisini işaretlenir soyut olarak.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4570 oluşturur.  
  
```  
// C4570.cpp  
// compile with: /clr /W3 /c  
ref struct X {   // C4570  
// try the following line instead  
// ref class X abstract {  
   virtual void f() abstract;  
};  
```