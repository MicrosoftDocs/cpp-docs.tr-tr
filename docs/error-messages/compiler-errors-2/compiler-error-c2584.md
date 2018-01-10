---
title: "Derleyici Hatası C2584 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2584
dev_langs: C++
helpviewer_keywords: C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5a8e28a6e57273d9609a8658b1e963a269b52e2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2584"></a>Derleyici Hatası C2584
'Class': doğrudan temel 'Base2' erişilemez; zaten bir 'Base1' taban  
  
 `Class`doğrudan zaten türetilen `Base1`. `Base2`Ayrıca türeyen `Base1`. `Class`öğesinden türetilen olamaz `Base2` (dolaylı olarak) içinden devralma anlamına çünkü `Base1` yeniden olmayan yasal olduğundan `Base1` zaten bir doğrudan temel sınıftır.  
  
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