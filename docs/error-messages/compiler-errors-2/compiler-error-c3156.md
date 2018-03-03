---
title: "Derleyici Hatası C3156 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3156
dev_langs:
- C++
helpviewer_keywords:
- C3156
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f6bfb5e9af810d9126617e960a7da6d98d6fab4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
