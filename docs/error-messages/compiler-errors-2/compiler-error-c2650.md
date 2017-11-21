---
title: "Derleyici Hatası C2650 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2650
dev_langs: C++
helpviewer_keywords: C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c3352820434c8d794d4980a606cb945bd8ecc4a8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2650"></a>Derleyici Hatası C2650
'işleci': sanal işlev olamaz  
  
 A `new` veya `delete` işleci bildirilen `virtual`. Bu işleçleri `static` üye işlevleri ve olamaz `virtual`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2650 oluşturur:  
  
```  
// C2650.cpp  
// compile with: /c  
class A {  
   virtual void* operator new( unsigned int );   // C2650  
   // try the following line instead  
   // void* operator new( unsigned int );  
};  
```