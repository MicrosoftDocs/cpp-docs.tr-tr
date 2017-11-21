---
title: "Derleyici Hatası C2849 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2849
dev_langs: C++
helpviewer_keywords: C2849
ms.assetid: e28f6b3e-e0e7-4f92-b006-ebaa81d368e6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 649c4ed4231518c7604f0a7f32ceb5a9632a4f71
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2849"></a>Derleyici Hatası C2849
'yıkıcı': yıkıcı bir arabirim olamaz  
  
 Visual C++ [arabirimi](../../cpp/interface.md) bir yıkıcı sahip olamaz.  
  
 Aşağıdaki örnek C2849 oluşturur:  
  
```  
// C2849.cpp  
// compile with: /c  
__interface C {  
   ~C();   // C2849 destructor not allowed in an interface  
};  
```