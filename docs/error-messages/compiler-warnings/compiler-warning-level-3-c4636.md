---
title: "Derleyici Uyarısı (Düzey 3) C4636 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4636
dev_langs: C++
helpviewer_keywords: C4636
ms.assetid: 59112a0f-850f-41c6-bd84-8ae8dc84706a
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e8bec09279dcb18753575ed496812d5565e2e62b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4636"></a>Derleyici Uyarısı (Düzey 3) C4636
XML belge açıklaması 'oluşturmak için ' uygulanan: etiketi boş gerekli '' özniteliği.  
  
 Gibi bir etiket `cref`, bir değere sahip değil.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4636 oluşturur.  
  
```  
// C4636.cpp  
// compile with: /clr /doc /W3 /c  
/// <see cref=''/>  
// /// <see cref='System::Exception'/>  
ref struct A {   // C4636  
   void f(int);  
};  
  
// OK  
/// <see cref='System::Exception'/>  
ref struct B {  
   void f(int);  
};  
```