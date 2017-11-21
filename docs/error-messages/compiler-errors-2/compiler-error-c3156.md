---
title: "Derleyici Hatası C3156 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3156
dev_langs: C++
helpviewer_keywords: C3156
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 793b143fa42e790610a086782c4bf99369965e1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3156"></a>Derleyici Hatası C3156
'class': bir yönetilen yerel tanımını ya da WinRT türüne sahip olamaz  
  
 Bir işlev tanımı veya yönetilen bir ya da WinRT bildirimi içeremez sınıf, yapı veya arabirim.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3156 oluşturur.  
  
```  
// C3156.cpp  
// compile with: /clr /c  
void f() {  
   ref class X {};   // C3156  
   ref class Y;   // C3156  
}  
```  
