---
title: "Derleyici Hatası C2633 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2633
dev_langs: C++
helpviewer_keywords: C2633
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: be00f8dd1387aebb68fd4031006ad73e01295263
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2633"></a>Derleyici Hatası C2633
'tanımlayıcısı': 'inline' olan oluşturucuları için yalnızca yasal depolama sınıfı  
  
 Bir oluşturucu satır içi dışındaki bir depolama sınıfı olarak bildirilir.  
  
 Aşağıdaki örnek C2633 oluşturur:  
  
```  
// C2633.cpp  
// compile with: /c  
class C {  
   extern C();   // C2633, not inline  
   inline C();   // OK  
};  
```