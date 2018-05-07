---
title: Derleyici Hatası C2584 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2584
dev_langs:
- C++
helpviewer_keywords:
- C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae9ea7a4b0ce44231925f4231c5876f352765ad6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2584"></a>Derleyici Hatası C2584
'Class': doğrudan temel 'Base2' erişilemez; zaten bir 'Base1' taban  
  
 `Class` doğrudan zaten türetilen `Base1`. `Base2` Ayrıca türeyen `Base1`. `Class` öğesinden türetilen olamaz `Base2` (dolaylı olarak) içinden devralma anlamına çünkü `Base1` yeniden olmayan yasal olduğundan `Base1` zaten bir doğrudan temel sınıftır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2584 oluşturur.  
  
```  
// C2584.cpp  
// compile with: /c  
struct A1 {  
   virtual int MyFunction();  
};  
  
struct A2 {  
    virtual int MyFunction();  
};  
  
struct B1: public virtual A1, virtual A2 {  
    virtual int MyFunction();  
};  
  
struct B2: public virtual A2, virtual A1 {  
    virtual int MyFunction();  
};  
  
struct C: virtual B1, B2 {  
    virtual int MyFunction();  
};  
  
struct Z : virtual B2, virtual C {   // C2584  
// try the following line insted  
// struct Z : virtual C {  
    virtual int MyFunction();  
};  
```