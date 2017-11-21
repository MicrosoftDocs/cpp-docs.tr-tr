---
title: "Derleyici Hatası C2806 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2806
dev_langs: C++
helpviewer_keywords: C2806
ms.assetid: 7c9ff1f4-1590-4c47-991d-b1075a173b48
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ddecb9434866d65bffba30bf7728ce82e84d6b46
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2806"></a>Derleyici Hatası C2806
çok fazla biçimsel parametresi 'işleci işleci' olan  
  
 Aşırı yüklenmiş bir işleç çok fazla parametre yok.  
  
 Aşağıdaki örnek C2806 oluşturur:  
  
```  
// C2806.cpp  
// compile with: /c  
class X {  
public:  
   X operator++ ( int, int );   // C2806 more than 1 parameter  
   X operator++ ( int );   // OK  
} ;  
```