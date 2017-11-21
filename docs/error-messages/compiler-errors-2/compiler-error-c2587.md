---
title: "Derleyici Hatası C2587 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2587
dev_langs: C++
helpviewer_keywords: C2587
ms.assetid: 7637a2c7-35d4-4b5a-a8f2-515a7bda98fd
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dd0590e6d1fe6a41a3725e74d3d501fce6d509b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2587"></a>Derleyici Hatası C2587
'tanımlayıcısı': geçersiz kullanımı yerel değişkene varsayılan parametre olarak  
  
 Yerel değişkenler varsayılan parametreler olarak izin verilmez.  
  
 Aşağıdaki örnek C2587 oluşturur:  
  
```  
// C2587.cpp  
// compile with: /c  
int i;  
void func() {  
   int j;  
   extern void func2( int k = j );  // C2587 -- local variable  
   extern void func3( int k = i );   // OK  
}  
```