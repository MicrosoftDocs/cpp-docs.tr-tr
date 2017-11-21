---
title: "Derleyici Hatası C2808 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2808
dev_langs: C++
helpviewer_keywords: C2808
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6cf7da43f9f816406ad76151d7404fa2e24d1fbe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2808"></a>Derleyici Hatası C2808
birli 'işleci işleci' çok fazla biçimsel parametresi olan  
  
 Birli işleç nonvoid parametre listesi vardır.  
  
 Aşağıdaki örnek C2808 oluşturur:  
  
```  
// C2808.cpp  
// compile with: /c  
class X {  
public:  
   X operator! ( X );   // C2808 nonvoid parameter list  
   X operator! ( void );   // OK  
};  
  
```